### 2591.Distribute-Money-to-Maximum-Children

首先考虑无解的情况。当money<children时，不能保证每个人都能分到钱；当children=1且money=4时，只有一个人必然拿到4块钱。这两种情况都是无解。

其他情况下，既然有解，那么每个人必然都拿到了一块钱，所以我们先扣除这部分“保底”的钱，即令`d = money - children`。因为我们希望尽量多地凑出8来，所以我们考察`k=d/7`，就是最多能分出8块钱的人数，剩余`r=d%7`块钱无法再凑出一个8块了。

那么是否意味着答案就是k呢？有一种特殊情况，就是剩余了4块钱且它恰好只分配给最后一个人。这种情况下是违反规则的，所以我们必须再让渡出一个8块钱的人，与最后一个人混合再打散避免出现4的情况. 这种情况下，真正能分得8块钱的人数就是k-1.