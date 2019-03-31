---
layout: post
title:      "Knapsack Algorithm"
date:       2019-03-31 11:28:50 +0000
permalink:  knapsack_algorithm
---


The knapsack problem or rucksack problem is a problem in combinatorial optimization: Given a set of items, each with a weight and a value, determine the number of each item to include in a collection so that the total weight is less than or equal to a given limit and the total value is as large as possible. It derives its name from the problem faced by someone who is constrained by a fixed-size knapsack and must fill it with the most valuable items.

The problem often arises in resource allocation where there are financial constraints and is studied in fields such as combinatorics, computer science, complexity theory, cryptography, applied mathematics, and daily fantasy sports.
A 1998 study of the Stony Brook University Algorithm Repository showed that, out of 75 algorithmic problems, the knapsack problem was the 19th most popular and the third most needed after suffix trees and the bin packing problem.

Knapsack problems appear in real-world decision-making processes in a wide variety of fields, such as finding the least wasteful way to cut raw materials,[4] selection of investments and portfolios,[5] selection of assets for asset-backed securitization,[6] and generating keys for the Merkle–Hellman and other knapsack cryptosystems.

Here is an implementation of this algorithm in Javascript.

We have a limited amount in the wallet and munuItems with costs and calories assigned. What is the most calories we can buy with our money?

function recursiveKnapSack(wallet, menuItems) {
     const n = menuItems.length;
     if (wallet <= 0)  return 0;
     //console.log(wallet)
     //console.log(menuItems)
     let maxCal = 0;
     for (let i = 0; i < n; i++) {
       //console.log("i",i)
        if (menuItems[i].price <= wallet ) {
           let newCal = menuItems[i].calories + recursiveKnapSack(wallet - menuItems[i].price, menuItems); //solution for when we spent money on the item i.
           maxCal= (maxCal>newCal) ? MaxCal : newCal
           //console.log("newCal:",newCal)
         }

         //console.log("maxCal",maxCal)
     }
     return maxCal;
   }


function  nonRecursiveKnapSack( wallet, menuItems) {
         let n = menuItems.length;
         let answers  = []; //answer[i] is solution for when wallet has i cents, initially filled with 0
         for (let i=0; i<n; i++){
           answers.push(0)
         }
         for (let currMoney = 1; currMoney <=wallet; currMoney++  ) {
            let maxCal = answers[currMoney-1];
            for (let i = 0; i < n; i++) {
               if (menuItems[i].price <= wallet) {
                 let prevCal = answers[currMoney - menuItems[i].price];
                  let newCal = menuItems[i].calories + prevCal;
                   maxCal= (maxCal>newCal) ? MaxCal : newCal
                 }
            }
            answers[currMoney] = maxCal;
         }
         return answers[wallet];
      }

