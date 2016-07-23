C
=

题目大意
--------

数轴上n个点，每个点距离源点的距离x[i]，价值w[i]，从0点单向出发，每一步都停在一点上，最终停在n点上
val = sum { sqrt( abs( x[i] - x[i-1] - len ) ) } / sum { b[i] }
目标使val最小，打印路径方案

思路及做法
----------

分数规划，二分val，dp验证是否合法，
dp[i] = F(val) = sum { sqrt( abs( x[i] - x[i-1] - len ) ) } - sum { b[i] } * val
dp[i] = dp [j] + sqrt( abs( x[i] - x[j] - len ) - b[i] * val

时间复杂度(n^2 logn)


AC code
-------

D
=

题目大意
--------

一个0、1矩阵，每行每列有2个1，已知前m行状态，求可能的状态数

思路及做法
----------

dp[i][j][k]：第i行剩j个位置放2个1，剩k个位置放1个1

dp[i][j][k] 

-> dp[i+1][j-2][k+2] += dp[i][j][k] * ( j * (j-1) / 2 )

-> dp[i+1][j-1][k] += dp[i][j][k] * j * k
            
-> dp[i+1][j][k-2] += dp[i][j][k]* ( k * (k-1) / 2 )

AC code
-------
