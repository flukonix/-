#task_1_screen_2

def re_list(lst):

    return lst[::-1]

r_list = [1,2,3,4,5]

r_list = re_list(r_list)

print(r_list)



#task_2_screen_1

def change(lst):

    lst[0],lst[-1] =  lst[-1], lst[0]

    return lst

print(change([1,2,3,4,5]))



#task_3_screen_1

def to_list(*args):

    return list(args)

print(to_list(1,2,3,4,5))



#task_4_screen_1

def useless(s):

    return max(s)/len(s)

print(useless([1,2,3,4,5]))



#task_5_screen_1

def list_sort(lst):

    for x in range(len(lst)-1):

        for y in range(len(lst)-1):

            if abs(lst[y]) < abs(lst[y+1]):

                f = lst[y]

                l = lst[y+1]

                lst[y] = l

                lst[y+1] = f

    return lst

print(f"Список в порядке убывания абсолютного значения чисел{list_sort([-1,-3,78,-12,2,-56,44,56])}")



#task_6_screen_1

def all_eq(lst):

    max_str = lst[0]

    for i in lst:

        if len(i) > len(max_str):

            max_str = i

    for i, word in enumerate(lst):

        if len(word) < len(max_str):

            add = len(max_str) - len(word)

            for y in range(add):

                lst[i] += "_"

    return lst

print(all_eq(["puppy","array","beautiful","car"]))



#task_1_screen_2

def to_float(num):

    if num != int(num):

        return "Невозможно преобразовать"

    return float(num)

print(to_float(55))



#task_2_screen_2

def avg_5(a,b,c,d):

    return round((a*b*c*d)/4, 5)

print(avg_5(1.11,7.3,6.7,3.4))



#task_3_screen_2

def mul_to_int(a,b):

    if a*b%1 == 0:

        return int(a*b)

    return a*b

print(mul_to_int(1.4,2))



#task_4_screen_2

def find_r(v):

    return ((3*v)/(4*3.14))**(1/3)

print(find_r(523.33))



#task_1_screen_3

def dislike_6(a):

    if a == 6:

        return "Только не 6"

    return True

print(dislike_6(5))

print(dislike_6(6))



#task_2_screen_3

def help_bool(letter):

    letter = letter.upper()

    if letter == "к":

        return "Коммутативность — свойство бинарной операции «», заключающееся в возможности перестановки аргументов: для любых элементов."

    elif letter == "а":

        return "Ассоциати́вность — свойство бинарной операции, заключающееся в возможности осуществлять последовательное применение формулы в произвольном порядке к элементам."

    elif letter == "д":

        return "Дистрибути́вность — свойство согласованности двух бинарных операций, определённых на одном и том же множестве."

    elif letter == "м":

        return "правило де Мо́ргана — логические правила, связывающие пары логических операций при помощи логического отрицания."

    else:

        return "к - коммутативность\nа - ассоциативность\nд - дистрибутивность\nм - правило де Моргана"

print(help_bool("м"))



#task_1_screen_4

#смотреть task_1_screen_1



#task_2_screen_4

#смотреть task_2_screen_1



#task_3_screen_4

#смотреть task_3_screen_1



#task_4_screen_4

#смотреть task_4_screen_1



#task_1_screen_5

#смотреть task_5_screen_1



#task_2_screen_5

#смотреть task_6_screen_1



#task_1_screen_6

def to_dict(lst):

    dt = {}

    for i in lst:

        dt[i] = i

    return dt

print(to_dict(["s","fig"]))



#task_2_screen_6

my_dict = {"first_one": "we can do it"}

def biggest_dict(**kwargs):

    global my_dict

    my_dict.update(**kwargs)

    return my_dict

print(biggest_dict(dog="Brock", cat="r"))



#task_3_screen_6

from collections import Counter

def count_it(sequence):

    counter_top3 = Counter(sequence).most_common(3)

    counter_top3 = dict(counter_top3)

    new_dict = {}

    for key, value in counter_top3.items():

        new_dict[int(key)] = value

    return new_dict

print(count_it("184709064732"))



#task_4_screen_6

dct = {"word": "red", "item": "box", "pizza": "pipironiki", "school": "teacher", "car": "BMW"}

first = list(dct.values())[0]

second = list(dct.values())[-1]

dct[list(dct.keys())[0]] = second

dct[list(dct.keys())[-1]] = first

del(dct[list(dct.keys())[1]])

dct["new_key"] = "new_value"

print(dct)



#task_1_Строки_1

def search_substr(subst,st):

    if subst.lower() in st.lower():

        return "Есть контакт!"

    else:

        return "Мимо!"

print(search_substr("world", "hello world"))



#task_2_Строки_1

def first_last(letter, st):

    turp = (st.find(letter), st.rfind(letter))

    return turp

print(first_last("w","eww"))



#task_3_Строки_1

#from collections import Counter уже вызывал

def top3(st):

    count3 = Counter(st.replace(' ', '')).most_common(3)

    return ', '.join([f'{letter} - {i}' for letter, i in count3])

print(top3("ajkfjahfghagfwya wduwjadhawndga"))



#task_4_Строки_1

def camel(st):

    st = st.lower()

    st = list(st)

    lst_i = []

    lst_l = []

    for i in range(len(st)):

        if st[i] == "," or st[i] == "." or st[i] == "!" or st[i] == " " or st[i] == ":" or st[i] == "-":

            lst_i.append(i)

            lst_l.append(st[i])

            st[i] = "#"

    st = "".join(st).replace("#","")

    st = list(st)

    for i in range(len(st)):

        if i % 2 == 0:

            st[i] = st[i].upper()

    st = "".join(st)

    for i in range(len(lst_i)):

        st = st[:lst_i[i]] + lst_l[i] + st[lst_i[i]:]

    return st

print(camel("Привет мой друг"))



#task_1_Строки_2

def shortener(st):

    while "(" in st or ")" in st:

        left_s = st.rfind("(")

        right_s = st.find(")", left_s)

        st = st.replace(st[left_s:right_s + 1], "")

    return st

print(shortener("ка(кк(акаы)пкы)пу(а)с((в)а)тка)"))



#task_2_Строки_2

def cleaned_str(st):

    clean_lst = []

    for s in st:

        if s != '@':

            clean_lst.append(s)

        elif s == '@' and clean_lst:

            clean_lst.pop()

    return ''.join(clean_lst)

print(cleaned_str("сварка@@@@@лоб@ну@"))

#Screen 1

def rock_paper_shears(p1, p2):

    if p1 == "Камень" and p2 == "Ножницы": return "Первый игрок выйграл"

    elif p1 == "Ножницы" and p2 == "Бумага": return "Первый игрок выйграл"

    elif p1 == "Бумага" and p2 == "Камень": return "Первый игрок выйграл"

    elif p1 == p2: return "Ничья"

    else: return "Второй игрок выйграл"

print(rock_paper_shears("Бумага", "Ножницы"))



#Screen 10

def can_or_not(lst_coins):

    if len(lst_coins) % 3 == 0: return "Получится"

    return "Не получится"

print(can_or_not(["coin", "coin", "coin", "coin", "coin"]))



#Screen 2

def do_not_shout(st):

   st = list(st)

   ind = []

   r = []

   for i in range(len(st)):

       if st[i] == "!" or st[i] == "?":

           for y in range(len(st)-i):

               if st[y+i] != "?" or st[y+i] != "?":

                   break

           ind.append(i)

   for i in range(len(ind)-1):

       if ind[i] + 1 != ind[i+1]:

           ind[i] = 0

           r.append(i)

   ind = ind[r[-1]+1:]

   st = "".join(st)

   if ("?" in st[ind[0]:] and not "!" in st[ind[0]:]) or ("!" in st[ind[0]:] and not "?" in st[ind[0]:]):

       if st[ind[0]:].find("?") > st[ind[0]:].find("!"):

           st = st[:ind[0]] + "?"

       elif st[ind[0]:].find("?") < st[ind[0]:].find("!"):

           st = st[:ind[0]] + "!"

   if "?" in st[ind[0]:] and "!" in st[ind[0]:]:

       if st[ind[0]:].find("?") < st[ind[0]:].find("!"):

           st = st[:ind[0]] + "?!"

       elif st[ind[0]:].find("?") > st[ind[0]:].find("!"):

           st = st[:ind[0]] + "!?"

   return st

print(do_not_shout("При?вет ??!мой друг?!!!!"))



#Screen 3

def black_jack(lst):

    return True if sum(lst) > 21 else False

print(black_jack([11, 10]))



#Screen 4

def plus_in_str(st):

    s = 0

    n = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9"]

    ss = []

    for i in range(len(st)):

        if st[i] in n:

            ss.append(st[i])

        else:

            ss.append("0")

    ss = "".join(ss)

    ss = ss.split("0")

    for i in range(len(ss)):

        if ss[i] == "":

            ss[i] = "0"

    for i in range(len(ss)):

        s += int(ss[i])

    return s

print(plus_in_str("абвгд7ап67фдрвц891офал1"))



#Screen 5

def l(st):

    s = st.replace("+", "")

    ll = 0

    for i in range(1, len(st)-1):

        if st[i] != "+" and st[i-1] == "+" and st[i+1] == "+":

            ll += 1

    return True if len(s) == ll else False

print(l("+а+б+в+г++д++"))



#Screen 6

def to_24(t):

    if "pm" in t:

        t = t.replace(" pm", "")

        time = t.split(":")

        t = t.split(":")

        if int(time[0]) + 12 == 24:

            x = "00"

        else:

            x = str(int(time[0]) + 12)

        t[0] = x

        return ":".join(t)

    else:

        t = t.replace("am", "")

    return t

print(to_24("12:34 pm"))



#Screen 7

def check_pass(p):

    ad = 0

    is_number = False

    is_letter = False

    is_upper = False

    if len(p) >= 8:

        ad += 1

    if "@" in p or "_" in p or "*" in p or "&" in p or "#" in p:

        ad += 1

    for item in p:

        try:

            if int(item) in range(0,10):is_number = True

        except ValueError:

            if item == item.upper(): is_upper = True

            is_letter = True

    if is_number: ad += 1

    if is_letter: ad += 1

    if is_upper: ad += 1

    return f"{ad} балла"

print(check_pass("kfr_12yT"))



#Screen 8

def from_int_to_str(integer):

    length = len(str(integer))

    nums = {"1": "один", "2": "два", "3": "три", "4": "четыре", "5": "пять", "6": "шесть", "7": "семь", "8": "восемь", "9": "девять",

            "10": "десять", "11": "одиннадцать", "12": "двенадцать", "13": "тринадцать", "14": "четырнадцать", "15": "пятнадцать", "16": "шестнадцать", "17": "семнадцать", "18": "восемнадцать", "19": "девятнадцать",

            "20": "двадцать", "30": "тридцать", "40": "сорок", "50": "пятьдесят", "60": "шестьдесят", "70": "семьдесят", "80": "восемьдесят", "90": "девяносто",

            "100": "сто", "200": "двести", "300": "триста", "400": "четыреста", "500": "пятьсот", "600": "шестьсот", "700": "семьсот", "800": "восемьсот", "900": "девятьсот"}

    name = ""

    if str(integer) in nums:

        return nums[str(integer)]

    if integer == 0:

        return "0"

    if len(str(integer)) == length:

        name += f"{nums[str(int(str(integer)[0])*(10**(length - 1)))]} "

        integer = int(integer) % (10**(length - 1))

        if str(integer) in nums:

            name += nums[str(integer)]

        else:

            name += f"{nums[str(int(str(integer)[0]) * 10)]} "

            integer = int(integer) % 10

            name += nums[str(integer)]

    return name

print(from_int_to_str(109))



#Screen 9

def luck(n):

    val = 0

    for i in range(10**(n-1), 10**n):

        lst = []

        for n in str(i):

            lst.append(int(n))

        if len(lst) % 2 != 0:

            q = len(lst) // 2

            if sum(lst[:q]) == sum(lst[q+1:]):

                val += 1

        else:

            q = len(lst) // 2

            if sum(lst[:q]) == sum(lst[q:]):

                val += 1

    return val

print(luck(4))

#Screen 10

def xy (x,y):

    lst_xy = []

    for i in range(len(x)):

        tr = (x[i], y[i])

        lst_xy.append(tr)

    return lst_xy

print(xy([3,2,1],[1,2,3]))



#Screen 11

def hello(lst):

    for i in range(len(lst)):

        print(f"Привет {lst[i]}")

hello(["Миша", "Петя", "Маша"])



#Screen 12

def double(st):

    for i in range(len(st)):

        if st[i].lower() == st[i+1].lower():return True

    return 0

print(double("Деревянный"))



#Screen 13

def without_space(st):

    st = list(st)

    if st[0] == " ":

        st[0] = ""

    if st[-1] == " ":

        st[-1] = ""

    st.append("0")

    for i in range(len(st)-1):

        if st[i] == " " and st[i] == st[i+1]:

            st[i] = ""

        if st[i] == " " and st[i+1] == "." or st[i+1] == "," or st[i+1] == ":" or st[i+1] == "!":

            st[i] = ""

    st.pop()

    return "".join(st)

print(without_space(" Привет мой   друг   ,       ты капуста  . "))



#Screen 14

def m(h, r):

    return round(3.14*(r**2)*h*1000,2)

print(m(0.15,0.05))



#Screen 15

def s(st):

    st = st.split(", ")

    sum = 1

    for i in range(len(st)):

        sum *= int(st[i])

    return sum

print(s("1, 2, 3"))



#Screen 16

def v(n):

    s = 0

    for i in range(n):

        x = int(input(f"Введите длину коробки {i+1} "))

        y = int(input(f"Введите ширину коробки {i + 1} "))

        z = int(input(f"Введите высоту коробки {i + 1} "))

        s += x*y*z

    return s

#print(v(3))



#Screen 17

def length(a,b):

    return round(abs(((b["x"] - a["x"])**2 + (b["y"] - a["y"])**2)**0.5), 3)

print(length({"x": 2, "y": 1},{"x": 3, "y": 4}))



#Screen 18

def language(st):

    st = st.replace("е", "3")

    st = st.replace("Е", "3")

    st = st.replace("а", "4")

    st = st.replace("А", "4")

    return st

print(language("Афигеть язык хакера!"))



#Screen 19

def up(lst):

    ls = []

    for i in range(len(lst)):

        ls.append(sum(lst[:i]) + lst[i])

    return ls

print(up([1,2,3,4,5,6]))



#Screen 20

def up_down(lst):

    return "Возрастает" if lst[0] < lst[-1] else "Убывает"

print(up_down([1,2,3,4,5]))



#Screen 21

def med(lst):

    lst.sort()

    l = len(lst)

    if l % 2 == 0:

        return (lst[l//2] + lst[l//2-1]) / 2

    else:

        return lst[l//2]

print(med([2,2,6,8,2,10,3]))



#Screen 7

def device():

    al = {1: "А", 2: "B", 3: "C", 4: "D", 5: "E", 6: "F", 7: "G", 8: "H", 9: "I",

          10: "J", 11: "K", 12: "L", 13: "M", 14: "N", 15: "O", 16: "P", 17: "Q", 18: "R", 19: "S",

          20: "T", 21: "U", 22: "V", 23: "W", 24: "X", 25: "Y", 26: "Z"}

    st = input("Введите слово с помощью клавиши 1 ")

    st = st.split(" ")

    for i in range(len(st)):

        st[i] = al[len(st[i])]

    return "".join(st)

#print(device())



#Screen 8

def remake(st):

    st = list(st)

    for i in range(len(st)):

        if st[i] == st[i].lower():

            st[i] = st[i].upper()

        else:

            st[i] = st[i].lower()

    st = st[::-1]

    return "".join(st)

print(remake(".гурД йоМ тевирП"))



#Screen 9

def i_am_not_have_enemi(lst, enem):

    for i in range(len(enem)):

        if enem[i] in lst:

            lst.remove(enem[i])

    return lst

print(i_am_not_have_enemi(["Ваня", "Таня", "Маша", "Нина", "Миша", "Вика"], ["Ваня", "Маша"]))
