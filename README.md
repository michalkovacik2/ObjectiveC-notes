# ObjectiveC-notes

- **Zakladne rozdiely**
  - Objective C používa messaging structure -> runtime rozhodne, ktorý kód bude spustený. Pri C++ to bolo na kompilátore. Keď sa pri C++ použije
    polymorfizmus, tak musíme mať Virtuálnu tabuľku, aby sme vedeli zavolať správnu implementáciu. Pri Objective C to netreba, lebo vždy sa 
    rozhoduje runtime. (dynamic binding). Typ objektu sa zistuje Runtime.
  - Všetky objekty sú vždy na heape (nemôžu byť na stacku). Jediná výnimka ak použijú C štruktúru tá môže byť na stacku (performance reasons) :D
  - 
  - 

*Objective C*
```objective-c
	Object * obj = [Object new];
	[obj performWith:parameter1 and parameter2];
```
*C++*
```cpp
	Object * obj = new Object;
	obj->perform(parameter1, parameter2);
```

*Objective C*
```objective-c
  NSNumber *someNumber = [NSNumber numberWithInt:1];
  
  // Tato literal syntax mi nefungovala (pozeral som Objective C v2.0), iba stringy isli
  NSNumber *someNumber = @1; // Identicka syntax ako hore
  NSNumber *someNumber2 = @3.14159;
  NSNumber *expression = @(someNumber * someNumber2);
  NSArray *animals = @[@"cat", @"dog", @"mouse"];

  // Ukazka Dictionary [hodnota : kluc], POZOR immutable, ak chcem menit treba NSMutableDictionary
  NSString *s = @"key2";

  NSDictionary *dict = 
  [NSDictionary dictionaryWithObjectsAndKeys:
    @"value1", @"key1",
    @"value2", @"key2",
    [NSNumber numberWithInt:28], @"key3"];

  NSLog([dict objectForKey:@"key1"]); // value1
  NSLog([dict objectForKey:s]);       // value2

  // NSMutableDictionary
  NSMutableDictionary *dict = [NSMutableDictionary dictionaryWithObjectsAndKeys:
    @"value1", @"key1",
    @"value2", @"key2",
    [NSNumber numberWithInt:28], @"key3"];

  NSLog([dict objectForKey:@"key1"]); // value1
  NSLog([dict objectForKey:s]);       // value2

  [dict setObject:@"change2" forKey:@"key2"];
  NSLog([dict objectForKey:@"key2"]); // change2
```
