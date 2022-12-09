# Final-Cut-and-Logic-Pro-Reset
#Final Cut Pro Reset

#mv -v ~/Library/Application\ Support/.ffuserdata ~/.Trash![image](https://user-images.githubusercontent.com/47684137/206750684-32afa7aa-12b5-4fff-958e-4c9c45133727.png)

#!/usr/bin/swift
import Foundation

let path = URL(fileURLWithPath: NSString(string: "~/Library/Application Support/.ffuserdata").expandingTildeInPath)
let data = try! NSData(contentsOf: path) as Data
let dictionary = try! NSKeyedUnarchiver.unarchiveTopLevelObjectWithData(data) as! NSDictionary
let mutableDictionary = dictionary.mutableCopy() as! NSMutableDictionary

for (key, value) in mutableDictionary {
  if value is NSDate {
    mutableDictionary[key] = Date()
  }
}

try! NSKeyedArchiver.archivedData(withRootObject: mutableDictionary, requiringSecureCoding: false).write(to: path)

print("You'd better buy it")

![image](https://user-images.githubusercontent.com/47684137/206749905-2eb438f4-99b7-4dc6-89c3-31cee60f06da.png)

#Logic Pro Reset
mv -v ~/Library/Application\ Support/.lpxuserdata ~/.Trash![image](https://user-images.githubusercontent.com/47684137/206750567-e4006301-bbca-4cc2-a744-4c5d04f78962.png)
