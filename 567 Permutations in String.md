1. Wrong code (time limit exceeded):
2. class Solution:
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
