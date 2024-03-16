def main():
  
  cardnumber = input("Enter your credit card number (without separators): ")

  if verification(cardnumber):
    print("card number is valid")
  else:
    print("card number is invalid")

def verification(card_valid):

  rev_num = card_valid[::-1]

  def sumodd(nums):
    oddnum = nums[::2]
    sum_odd = 0
    for digit in oddnum:
      sum_odd += int(digit)
    return sum_odd

  def sumeven(nums):
    evennum = nums[1::2]
    sum_even = 0
    for digit in evennum:
      number = int(digit) * 2
      if number >= 10:
        sum_even += (number // 10) + (number % 10)
      else:
        sum_even += number
    return sum_even

  sum1 = sumodd(rev_num)
  sum2 = sumeven(rev_num)
  total = sum1 + sum2

  return total % 10 == 0  

if __name__ == "__main__":
  main()

