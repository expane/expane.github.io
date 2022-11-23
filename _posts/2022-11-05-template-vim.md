---
layout: post
title: vim配置文件
categories: [杂项]
tags: []
---

实际只需要前 5 行！简单实用！

```vim
filetype plugin indent on
set nu rnu ar acd sw=4 ts=4 sts=4 tgc mouse=a foldmethod=marker noswf
map <F7> :wa<CR>:!clear && g++ -DLOCAL -std=c++14 -O2 %<.cpp -o %< && bash -c "time ./%<"<CR>
map <F8> :wa<CR>:!clear && g++ -fsanitize=address,undefined -DLOCAL -std=c++14 -O2 %<.cpp -o %< && bash -c "time ./%<"<CR>
map <F9> :wa<CR>:!clear && ./tester.sh<CR>

map <C-B> <c-w>98\|<c-w>l<c-w>30\|<c-w>h
map <F10> ggd%O<ESC>:r!fortune; echo " */"<CR>k<C-V>gg0I * <ESC>r/:wa<CR>
```

最后一行娱乐用，可以向文件开头插入随机神秘文字。（不满意可以再按一次）（需要安装 `fortune`）
