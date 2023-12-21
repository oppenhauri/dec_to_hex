# dec_to_hex
the number in dec to hex
input1 = (15,14,13,12,11,10,9,8,7,6,5,4,3,2,1,0)
file_output = r"C:\Users\ASUS\Desktop\hex.txt"
length = len(input1)

output = []
for i in range(0, length, 1):
    temp = hex(input1[i])
    output.append(list(temp))
print(output)
# 处理合并数据
temp1 = '{}{}{}{}'
temp3 = '{}{}{}'
with open(file_output, 'w', encoding='utf-8') as w:
    w.write('[')
    for hex_list in output:
        length_hex = len(hex_list)
        if length_hex == 3:
            temp3 = temp3.format(hex_list[0], hex_list[1], hex_list[2])
            w.write(temp3)
            w.write(',')
            temp3 = '{}{}{}'

        else:
            temp1 = temp1.format(hex_list[0], hex_list[1], hex_list[2], hex_list[3])
            w.write(temp1)
            w.write(',')
            temp1 = '{}{}{}{}'
    w.write(']')
    w.close()
