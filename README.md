# Maximum-Score-After-Splitting-a-String
class Solution:
    def maxScore(self, s):
        max_score = 0
        zeros_left = 0
        ones_right = s.count('1')

        for i in range(len(s) - 1):
            if s[i] == '0':
                zeros_left += 1
            else:
                ones_right -= 1

            current_score = zeros_left + ones_right
            max_score = max(max_score, current_score)

        return max_score


if __name__ == "__main__":
    obj = Solution()

    input_str1 = "011101"
    input_str2 = "00111"
    input_str3 = "1111"

    output1 = obj.maxScore(input_str1)
    output2 = obj.maxScore(input_str2)
    output3 = obj.maxScore(input_str3)

    print(output1)  
    print(output2)  
    print(output3)  
