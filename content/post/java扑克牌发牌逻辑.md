---
title: "Java扑克牌发牌逻辑"
author: "ray"
cover: "/img/cover.jpg"
tags: ["java"]
date: 2019-05-31T14:22:46+08:00
draft: true
---

```
    package run;
   
    import java.lang.reflect.Array;
    import java.util.ArrayList;
    import java.util.Collections;
    
    /*
     * 1.准备牌
     * 2.洗牌
     * 3.发牌
     * 4.看牌
     * */
    
    public class PokerDemo {
        public static void main(String[] args) {
            //定义一个动态数组存储扑克
            ArrayList<String> poker = new ArrayList<>();
    
            //定义一个数组放牌的颜色
            //定义一个数组存储牌的13个序号
            //定义４个集合
            String[] colors = new String[]{"♥", "♠", "♣", "♦"};
            String[] numbers = {"2", "A", "K", "Q", "J", "10", "9", "8", "7", "6", "5", "4", "3"};
    
            //先把大王小王存储到动态数组中
            poker.add("大王");
            poker.add("小王");
    
            //循环嵌套牌的颜色和牌的数值，得到52张牌
            for (String number : numbers) {
                for (String color : colors) {
                    poker.add(color + number);
                }
            }
            Collections.shuffle(poker); //调用Collections 中的静态方法shuffle,无序的打乱poker的顺序
	 　 //定义4个动态数组分别存储3个玩家的牌和底牌
            ArrayList<String> player_one = new ArrayList<>();
            ArrayList<String> player_two = new ArrayList<>();
            ArrayList<String> player_three = new ArrayList<>();
            ArrayList<String> player_dipai = new ArrayList<>();
    
            for (int i = 0; i < poker.size(); i++) {
                //得到每次遍历的值通过动态数组的get()方法;
		String p = poker.get(i);
                if (i >= 51) {
                    player_dipai.add(p);
                } else if (i % 3 == 0) {
                    player_one.add(p);
                } else if (i % 3 == 1) {
                    player_two.add(p);
                } else if (i % 3 == 2) {
                    player_three.add(p);
                }
            }
    
            System.out.println("player_one :" + player_one);
            System.out.println("player_two :" + player_two);
            System.out.println("player_three :" + player_three);
            System.out.println("player_dipai: " + player_dipai);
        }
    }


```

