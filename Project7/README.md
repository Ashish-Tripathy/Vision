# Receptive Field Calculation for GoogLeNet

GoogLeNet Architecture
  ![alt text](https://cdn-images-1.medium.com/max/2600/1*ZFPOSAted10TPd3hBQU8iQ.png)
 
## Step by step Calculation</b>

The calculated recetive field is around <b>907</b> which should have been around 224 as claimed by paper.
All my calculations are in line with what was taught in the class except for the assumption that for each inception module I have considered only 5x5 for RF calculation as it gave the highest RF compared to maxpool and 3x3.
Please let me know where is the mistake and how we can calculate it correctly.

| Layer | Layer Type | k | s | Jin | RFin | RFout | Calculation text   |
|-------|------------|---|---|-----|------|-------|--------------------|
| 1     | Conv       | 7 | 2 | 1   | 1    | 7     | 1+(7-1)*1 = 7      |
| 2     | Maxpool    | 3 | 2 | 2   | 7    | 11    | 7+(3-1)*2 = 11     |
| 3     | conv       | 3 | 1 | 4   | 11   | 19    | 11+(3-1)*4 = 11    |
| 4     | Maxpool    | 3 | 2 | 4   | 19   | 27    | 19+(3-1)*4 = 27    |
| 5     | conv       | 5 | 1 | 8   | 27   | 59    | 27+(5-1)*8 = 59    |
| 6     | conv       | 5 | 1 | 8   | 59   | 91    | 59+(5-1)*8 = 91    |
| 7     | maxpool    | 3 | 2 | 8   | 91   | 107   | 91+(3-1)*8 = 107   |
| 8     | conv       | 5 | 1 | 16  | 107  | 171   | 107+(5-1)*16 = 171 |
| 9     | conv       | 5 | 1 | 16  | 171  | 235   | 171+(5-1)*16 = 235 |
| 10    | conv       | 5 | 1 | 16  | 235  | 299   | 235+(5-1)*16 = 299 |
| 11    | conv       | 5 | 1 | 16  | 299  | 363   | 299+(5-1)*16 = 363 |
| 12    | conv       | 5 | 1 | 16  | 363  | 427   | 363+(5-1)*16 = 427 |
| 13    | maxpool    | 3 | 2 | 16  | 427  | 459   | 427+(3-1)*16 = 459 |
| 14    | conv       | 5 | 1 | 32  | 459  | 587   | 459+(5-1)*32 = 587 |
| 15    | conv       | 5 | 1 | 32  | 587  | 715   | 587+(5-1)*32 = 715 |
| 16    | avg pool   | 7 | 1 | 32  | 715  | 907   | 715+(7-1)*32 = 907 |
