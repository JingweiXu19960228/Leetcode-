1. Wrong code

class Solution:
    def findAnagrams(self, s: str, p: str) -> List[int]:
        if len(s)<len(p):
            return []
        empty=[0]*26
        a=[0]*26
        b=[0]*26
        for i in p:
            a[ord(i)-ord('a')]+=1
            b[ord(i)-ord('a')]+=1
        
        res=[]
        ind=0
        for j in s:
            if j in p:
                a[ord(j)-ord('a')]-=1
            if (a==empty):
                res.append(ind-len(p)+1)
                a=b
            ind+=1
        return res


3. Thoughts:
(1). 
