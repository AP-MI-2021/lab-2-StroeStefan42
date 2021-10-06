def get_leap_years (start: int, end: int):
    list = []
    for i in range(start, end):
        if (i % 4 == 0 and i % 100 != 0) or i % 400 == 0:
            list.append(i)
    return list
def test_get_leap_years():
    assert get_leap_years(1995, 2014) == [1996, 2000, 2004, 2008, 2012]
    assert get_leap_years(1894, 1902) == [1896]
def get_perfect_squares (start: int, end: int):
    list = []
    i = 0
    while(i * i <= end):
        if(i*i >= start):
            list.append(i*i)
        i = i + 1
    return list
def test_get_perfect_squares():
    assert get_perfect_squares(5, 27) == [9, 16, 25]
    assert get_perfect_squares(101, 197) == [121, 144, 169, 196]
def is_palindrome(n):
    o = 0
    n2 = n
    while (n != 0):
        o = o * 10 + n % 10
        n = n // 10
    if o == n2:
        return True
    else:
        return False
def test_is_palindrome():
    assert is_palindrome(1991) == True
    assert is_palindrome(1823) == False
    assert is_palindrome(1725) == False
    assert is_palindrome(3) == True
def main():
    while True:
        print('1. Anii bisecti')
        print('2. Patrate perfecte')
        print('3. Palindrom')
        print('x. Iesire din program')
        optiune=input('Alege optiunea: ')
        if optiune == '1':
            start=int(input('Dati valoarea de start:'))
            end=int(input('Dati valoarea de sfarsit:'))
            list2 = get_leap_years(start, end)
            print(list2)
        elif optiune == '2':
            start=int(input('Dati valoarea de inceput:'))
            end=int(input('Dati valoarea de sfarsit:'))
            list2 = get_perfect_squares(start, end)
            print(list2)
        elif optiune == '3':
            n = int(input('Dati valoarea:'))
            if is_palindrome(n) == True:
                print("Este palindrom")
            else:
                print("Nu este palindrom")
        elif optiune == 'x':
            break
if __name__ == '__main__':
    main()