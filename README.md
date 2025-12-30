

Tumhe:

nums = ["102","473","251","814"]
queries = [[1,1],[2,3],[4,2],[1,2]]


Har query = [k, trim]

Steps for each query:

Har number ke last trim digits lo

In trimmed numbers ko numeric order me sort karo

Sorted list ka k-th smallest element ka original index return karo

🟡 Tum kya code kar rahe ho?

Tumne radix sort use kiya — aur woh bhi bahut smart tareeke se.

Tum har digit column par stable count sort kar rahe ho, right to left.

Step 1 — curr[]
curr = [0,1,2,3]


Iska matlab:

102 → index 0
473 → index 1
251 → index 2
814 → index 3


Tum actual numbers move nahi kar rahe,
tum sirf unke indices move kar rahe ho.

Step 2 — Last digit sort (i = 1)

Last digits:

Number	Index	Last digit
102	0	2
473	1	3
251	2	1
814	3	4

Sorted by last digit:

1 → 251 (2)
2 → 102 (0)
3 → 473 (1)
4 → 814 (3)


So curr ban jata hai:

[2,0,1,3]


Tum isko list.get(0) me store kar dete ho.

Step 3 — Last 2 digit sort (i = 2)

Ab tum yeh order use karte ho:

02, 73, 51, 14


Stable sort karte ho → result:

[0,3,2,1]


Store in list.get(1).

Step 4 — Last 3 digit sort (i = 3)

Full numbers:

102,814,251,473


Sorted:

[0,2,3,1]


Store in list.get(2).

🧠 Tumne kya banaya?

Tumne bana liya:

list[0] → trim = 1 sorted indices
list[1] → trim = 2 sorted indices
list[2] → trim = 3 sorted indices

🔥 Query handling
res[i] = list.get(trim-1)[k-1];


Matlab:

Trim length trim ke sorted list me jao
Usme se k-th smallest index nikaal lo

Exactly wahi jo question pooch raha hai
