1. Right code

class Solution:
    def palindromePairs(self, words: List[str]) -> List[List[int]]:
        
        def isPalindrome(word):
            if word == word[::-1]:
                return True
            else:
                return False
            
        wmap = {w:i for i,w in enumerate(words)}
        res = set()
        
        for idx, word in enumerate(words):
            if word and isPalindrome(word) and "" in wmap:
                nidx = wmap[""]
                res.add((idx,nidx))
                res.add((nidx,idx))
                
            rword = word[::-1]
            
            if word and rword in wmap:
                nidx = wmap[rword]
                if idx!=nidx:
                    res.add((idx,nidx))
                    res.add((nidx,idx))
            
            for i in range(1,len(word)):
                left,right = word[:i], word[i:]
                rleft,rright = left[::-1], right[::-1]
                
                if isPalindrome(left) and rright in wmap:
                    res.add((wmap[rright],idx))
                    
                if isPalindrome(right) and rleft in wmap:
                    res.add((idx,wmap[rleft]))
                    
        return list(res)
                
 2. Thoughts
 (1). The key is to understand the three ways to form a palindrome
 (2). Some details: line 16 and 23, need to check if word exists
 In line 16, because empty string itself is palindrome, so needs to be excluded
 In line 23, it can save time
