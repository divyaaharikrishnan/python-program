# python-program

#program to find  smallest substring


total_chars=256

def  max_distinct_character(str,n):
    count=[0]*total_chars

    for i in range(n):
        count[ord(str[i])] +=1

    max_distinct=0
    for i in range(total_chars):
        if(count[i] !=0):
            max_distinct+=1
    return max_distinct

def  smallest_substr(str):
    n=len(str)
    max_distinct = max_distinct_character(str,n)
    minl=n

    for i in range(n):
        for j in range(n):
            sub_str=str[i:j]
            sub_length=len(sub_str)
            sub_distinct_char = max_distinct_character(sub_str,sub_length)

            if (sub_length <minl and max_distinct == sub_distinct_char):
                minl=sub_length


    return minl

if __name__ =='__main__':
    str="abcda"
    l=smallest_substr(str)
    print(l)
