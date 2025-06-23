# 🚀 LeetCode POTD - Day 7

<table>
<tr>
<td align="left" width="400">
  <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*VOQU8CuPG34Gsd1yJCadOQ.png" width="100%"/>
</td>
</tr>
</table>

---

## 🧙‍♂️ 2138. Divide a String Into Groups of Size k


[Link to problem](https://leetcode.com/problems/divide-a-string-into-groups-of-size-k/)

---

## 🔥 Optimal Solution

```cpp
class Solution {
public:
    vector<string> divideString(string s, int k, char fill) {
        vector<string> result;
        int n = s.length();

        int i = 0;
        while(i < n) {
            int j       = (i + k - 1 >= n) ? n-1 : (i + k - 1);
            string temp = s.substr(i, j-i+1);

            if(j-i+1 < k) {
                int remain = k - (j-i+1);
                temp += string(remain, fill);
            }
            result.push_back(temp);

            i += k;
        }

        return result;
    }
};



