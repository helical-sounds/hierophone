# multiplier

control current circuitry

iabc = Vc/100k * (1k5 + 33k)/1k5

5 = 1.15ma
1.2 = 0.05 * (r + 33k)/r
1.2r = 0.05r + 1.65
1.15r = 1.65

0v   = 0ma
2.5v = 0.575ma
5v   = 1.15ma

OTA current out = 19.2 * iabc * vIn * 220/(100k+220)
vOut = vIn - (OTA current out * 47k)
vOut = vIn - (vIn * iabc * 0.042 * 47k)
vOut/vIn = Gain = 1 - iabc * 0.042 * 47k

Think control circuitry pot directions need flipping

0v input should be gain of 1

2.5v input should be gain of 0
2.5v == 0.575ma
0 = 1 - 0.575 * 0.042 * Rout
0.02415 Rout = 1
Rout should be 41k

5v input should be gain of -1
5v == 1.7ma
-1 = 1 - 1.7 * 0.042 * 28k
0.0714 Rout = 2
Rout should be 28k
