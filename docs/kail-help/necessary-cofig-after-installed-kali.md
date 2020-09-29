# Necessary Config After Installed Kali Linux

## Sources List
```
# kali source
deb http://http.kali.org/ kali-rolling main non-free contrib
deb-src http://http.kali.org/ kali-rolling main non-free contrib

# ustc source
deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib

# aliyun source
deb http://mirrors.aliyun.com/kali sana main non-free contrib
deb http://mirrors.aliyun.com/kali-security/ sana/updates main contrib non-free
deb-src http://mirrors.aliyun.com/kali-security/ sana/updates main contrib non-free

# tsinghua source
deb http://mirrors.tuna.tsinghua.edu.cn/kali kali-rolling main contrib non-free
deb-src https://mirrors.tuna.tsinghua.edu.cn/kali kali-rolling main contrib non-free
```

## Update Sources
> apt-get update

> apt-get upgrade

> apt-get clean
