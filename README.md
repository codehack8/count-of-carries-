# count-of-carries-
def count_carries(num1, num2):
    carries = 0
    carry = 0
    str_num1 = str(num1)
    str_num2 = str(num2)
    max_len = max(len(str_num1), len(str_num2))
    str_num1 = str_num1.zfill(max_len)
    str_num2 = str_num2.zfill(max_len)
    
    
    for i in range(max_len - 1, -1, -1):
        digit_sum = int(str_num1[i]) + int(str_num2[i]) + carry
        
        if digit_sum >= 10:
            carries += 1
            carry = digit_sum // 10
        else:
            carry = 0
    
    return carries


num1 = 1595
num2 = 9427
result = count_carries(num1, num2)
print(f"Number of carries: {result}")
