# Intuition
First handle the input word length and then check character by character whether it meets the validation
Approach
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
Initially, checked the input length restrictions. Then, addressed the edge cases where the word would meet the detection if it had all lowercase or all uppercase characters. Finally, validated the scenario where, if the first character was uppercase, the others should be lowercase
<!-- Describe your approach to solving the problem. -->

# Complexity
- Time complexity: $$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```csharp []
public class Solution {
    public bool DetectCapitalUse(string word) {    
        if (1 <= word.Length && word.Length <= 100) 
        {
            if (word.All(c => char.IsUpper(c)) || word.All(c => char.IsLower(c)))
                return true;

            return char.IsUpper(word[0]) ? word.Skip(1).All(x => char.IsLower(x)) : false;
        }
        else
            return false;
    }
}
```
