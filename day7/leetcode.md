# 3.罗马数字转整形

```c
int romanToInt(char * s){
    int len=strlen(s);
 int sum=0;
 for(int i=0;i<len;i++){
     char c=s[i];
  switch(c){
        case 'I':
        if(s[i+1]=='V') {sum+=4;i++;}
        else if(s[i+1]=='X') {sum+=9;i++;}
        else sum+=1;
        break;
        case 'V':
        sum+=5;
        break;
        case 'X':
        if(s[i+1]=='L') {sum+=40;i++;}
        else if(s[i+1]=='C') {sum+=90;i++;}
        else sum+=10;
        break;
        case 'L':
        sum+=50;
        break;
        case 'C':
        if(s[i+1]=='D') {sum+=400;i++;}
        else if(s[i+1]=='M') {sum+=900;i++;}
        else sum+=100;
        break;
        case 'D':
        sum+=500;
        break;
        case 'M':
        sum+=1000;
        break;
        default:
        break;
    }
 }
 return sum;
}
```

# 3

```c
int lengthOfLongestSubstring(char * s){
    int max_size = 0;
    int cur_size = 0;
    
    if(s == NULL)
        return 0;
    if(s[0] == '\0')
        return 0;

    int l = 0; // 用来存放子串最左边的位置
    int r = 1; // 用来存放子串右边位置，这个值不断右移，移动一次就与前面l位置开始到r-1的位置的值比较。
    while(s[r] != '\0')
    {
        for(int i=l; i<r; ++i)
        {
            if(s[r] == s[i]) // 找到相同的值
            {
                cur_size = r - l;
                l = i+1; // 更新l的位置

                if(max_size < cur_size)
                    max_size = cur_size;
            }
        }
        ++r;
    }

    cur_size = r-l;
    if(max_size < cur_size)
        max_size = cur_size;
    
    return max_size
}
```

# 1332

```c
int removePalindromeSub(char * s) {
    int n = strlen(s);
    for (int i = 0; i < n / 2; ++i) {
        if (s[i] != s[n - 1 - i]) {
            return 2;
        }
    }
    return 1;
}
```

