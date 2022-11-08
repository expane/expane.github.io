---
layout: post
title: 对拍脚本
categories: [杂项]
tags: []
---

```shell
#!/bin/bash
task= #题目名称
g++ $task.cpp -O2 -std=c++14 -o $task -lm & \
g++ dtmk.cpp -O2 -std=c++14 -o dtmk; wait

for ((i=1;i<=100;i++)); do
    echo "Test #"$i
    ./dtmk;
    ./$task & ./force; wait
    diff -q $task.out $task.ans
    if [ $? != 0 ]; then break; fi
done

```
