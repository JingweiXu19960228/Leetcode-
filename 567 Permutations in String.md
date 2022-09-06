1. Wrong code (time limit exceeded):
2. 
class Solution:
    def checkInclusion(self,s1: str, s2: str) -> bool:
        d1=defaultdict(int)
        d2=defaultdict(int)
        
        def isAnagram(s: str, t: str) -> bool:
            a=[0]*26
            for i in s:
                a[ord(i)-ord('a')]+=1
            for i in t:
                a[ord(i)-ord('a')]-=1
        
            for j in range(26):
                if a[j]!=0:
                    return False
                    break
            return True
        
        if len(s2)<len(s1):
            return False
        
        for k in range(len(s1)):
            d1[s1[k]]+=1
            
        i=0    
        
        for j in range(len(s1)):
            d2[s2[j]]+=1
            
        while j<len(s2)-1:
            if isAnagram(s1,s2[i:j+1]):
                return True
            i+=1
            j+=1
            
        if isAnagram(s1,s2[i:j+1]):
            return True
        else:
            return False
            
2. Right code 

class Solution:
    def checkInclusion(self,s1: str, s2: str) -> bool:
        if len(s2) < len(s1):
            return False
        c = Counter(s1)
        
        l = 0
        r = len(s1)-1
        s = Counter(s2[l:r])
        while r < len(s2):
            s[s2[r]]+=1
            if s==c:
                return True
            s[s2[l]]-=1
            # if s[s2[l]]==0:
            #     del s[s2[l]]
            l+=1
            r+=1
        
        
        return False


3. Thought

(1). Think of why the wrong code is inefficient
(2). In the right code, it seems that if I deleted line 58 and 59, it would still pass the test

