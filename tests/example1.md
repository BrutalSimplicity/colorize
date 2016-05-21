# Example 1

Here is an example of colorizer syntax highlighting the code blocks in an html file created from a markdown document.

## Python

```python
def luhn(n):
	r = [int(ch) for ch in str(n)][::-1]
	return (sum(r[0::2]) + sum(sum(divmod(d*2,10)) for d in r[1::2])) % 10 == 0
```

## C#

```csharp
public static class Luhn
    {
        public static bool LuhnCheck(this string cardNumber)
        {
            return LuhnCheck(cardNumber.Select(c => c - '0').ToArray());
        }
 
        private static bool LuhnCheck(this int[] digits)
        {
            return GetCheckValue(digits) == 0;
        }
 
        private static int GetCheckValue(int[] digits)
        {
            return digits.Select((d, i) => i % 2 == digits.Length % 2 ? ((2 * d) % 10) + d / 5 : d).Sum() % 10;
        }
    }
```

## Haskell

```haskell
import Data.Char (digitToInt)
luhn = (0 ==) . (`mod` 10) . sum . map (uncurry (+) . (`divMod` 10)) .
       zipWith (*) (cycle [1,2]) . map digitToInt . reverse
```

## Clojure

```clojure
(defn count-substring [txt sub]
  (count (re-seq (re-pattern sub) txt)))
```

## Java

```java
public class CountSubstring {
    public static int countSubstring(String subStr, String str){
        return (str.length() - str.replace(subStr, "").length()) / subStr.length();
    }
 
    public static void main(String[] args){
        System.out.println(countSubstring("th", "the three truths"));
        System.out.println(countSubstring("abab", "ababababab"));
        System.out.println(countSubstring("a*b", "abaabba*bbaba*bbab"));
    }
}
```

## Matlab

```matlab
% Count occurrences of a substring without overlap
length(findstr("ababababab","abab",0))
length(findstr("the three truths","th",0))

% Count occurrences of a substring with overlap
length(findstr("ababababab","abab",1))
```

## Sass

```sass
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 62.5%;
}

aside[role="complementary"] {
  float: right;
  width: 31.25%;
}
```

## Rust

```rust
fn is_leap(year: i32) -> bool {
    let factor = |x| year % x == 0;
    factor(4) && (!factor(100) || factor(400))
    }
}
```