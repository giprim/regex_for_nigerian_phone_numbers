##  JAVASCRIPT 

```js
const regex = /^(0)([789])([0-9])([0-9]{8})|(\+234)([789])([0-9])([0-9]{8})$/;
const str = `09037915328 +2349037915328`;
let m;

while ((m = regex.exec(str)) !== null) {
    // This is necessary to avoid infinite loops with zero-width matches
    if (m.index === regex.lastIndex) {
        regex.lastIndex++;
    }
    
    // The result can be accessed through the `m`-variable.
    m.forEach((match, groupIndex) => {
        console.log(`Found match, group ${groupIndex}: ${match}`);
    });
}
```

## JAVA 

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

final String regex = "^(0)([789])([0-9])([0-9]{8})|(\\+234)([789])([0-9])([0-9]{8})$";
final String string = "09037915328 +2349037915328";

final Pattern pattern = Pattern.compile(regex, Pattern.MULTILINE);
final Matcher matcher = pattern.matcher(string);

while (matcher.find()) {
    System.out.println("Full match: " + matcher.group(0));
    for (int i = 1; i <= matcher.groupCount(); i++) {
        System.out.println("Group " + i + ": " + matcher.group(i));
    }
}
```

## PHP 
```php
$re = '/^(0)([789])([0-9])([0-9]{8})|(\+234)([789])([0-9])([0-9]{8})$/';
$str = '09037915328 +2349037915328';

preg_match_all($re, $str, $matches, PREG_SET_ORDER, 0);

// Print the entire match result
var_dump($matches);
```
## PYTHON 

*coding=utf8*
*the above tag defines encoding for this document and is for Python 2.x compatibility*

```python
import re

regex = r"^(0)([789])([0-9])([0-9]{8})|(\+234)([789])([0-9])([0-9]{8})$"

test_str = "09037915328 +2349037915328"

matches = re.finditer(regex, test_str, re.MULTILINE)

for matchNum, match in enumerate(matches, start=1):
    
    print ("Match {matchNum} was found at {start}-{end}: {match}".format(matchNum = matchNum, start = match.start(), end = match.end(), match = match.group()))
    
    for groupNum in range(0, len(match.groups())):
        groupNum = groupNum + 1
        
        print ("Group {groupNum} found at {start}-{end}: {group}".format(groupNum = groupNum, start = match.start(groupNum), end = match.end(groupNum), group = match.group(groupNum)))
```

*Note: for Python 2.7 compatibility, use ur"" to prefix the regex and u"" to prefix the test string and substitution.*

