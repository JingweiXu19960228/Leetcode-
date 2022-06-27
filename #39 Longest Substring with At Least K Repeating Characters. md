    def longestSubstring(self, s: str, k: int) -> int:
        i=0
        maximum=0
        d=collections.defaultdict(int)
        for j in range(len(s)):
            d[s[j]]+=1
            while min(d.values())>=k:
                i+=1
            maximum=max(maximum,j-i)
        return maximum
                
