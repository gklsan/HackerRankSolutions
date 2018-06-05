# HackerRankSolutions

# solve-me-first
https://www.hackerrank.com/challenges/solve-me-first/problem
```
def solveMeFirst (a, b)
  # Hint: Type return a+b below   
  return (a+b)
end

val1 = gets.to_i
val2 = gets.to_i
sum = solveMeFirst(val1,val2)
print (sum)

```

Input:
```
2
3
```

Output:
```
5
```

# simple-array-sum
https://www.hackerrank.com/challenges/simple-array-sum/problem
```
#!/bin/ruby

def simpleArraySum(ar)
    ar.inject(&:+)
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

ar_count = gets.to_i

ar = gets.rstrip.split(' ').map(&:to_i)

result = simpleArraySum ar

fptr.write result
fptr.write "\n"

fptr.close()
```

Input:
```
6
1 2 3 4 10 11
```
Output:
```
31
```
# time-conversion
https://www.hackerrank.com/challenges/time-conversion/problem
```
#!/bin/ruby
require 'time'
#
# Complete the timeConversion function below.
#
def timeConversion(s)
    Time.strptime(s, "%H:%M:%S%P").strftime("%H:%M:%S")
end

fp = File.open(ENV['OUTPUT_PATH'], 'w')

s = gets.to_s.rstrip

result = timeConversion s

fp.write result
fp.write "\n"

fp.close()
```

Input:
```
07:05:45PM
```

Output:
```
19:05:45
```

# mini-max-sum
https://www.hackerrank.com/challenges/mini-max-sum/problem
```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the miniMaxSum function below.
def miniMaxSum(arr)
    res = arr.collect.with_index{|i, idx|
            arr_new = arr.dup
            arr_new.delete_at(idx)
            arr_new.inject(&:+)
        }
    puts "#{res.min} #{res.max}"

end

arr = gets.rstrip.split(' ').map(&:to_i)

miniMaxSum arr
```

Input:
```
1 2 3 4 5
```

Output:
```
10 14

```

# staircase

https://www.hackerrank.com/challenges/staircase/problem
```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the staircase function below.
def staircase(n)
    n.times{|i| puts "#{'#' * (i+1)}".rjust(n, " ") }
end

n = gets.to_i

staircase n
```

Input:
```
6 
```

Output:
```
     #
    ##
   ###
  ####
 #####
######
```

# plus-minus

https://www.hackerrank.com/challenges/plus-minus/problem
```
#!/bin/ruby

require 'json'
require 'stringio'

def printRes(data)
    "#{'%.5f' % data}"    
end
# Complete the plusMinus function below.
def plusMinus(arr)
    len = arr.length
    positives, negatives = arr.partition(&:positive?)
    zeroCount = negatives.count(0)
    puts printRes(positives.count/len.to_f)
    negatives.delete(0)
    puts printRes(negatives.size/len.to_f)
    puts printRes(zeroCount/len.to_f)
end

n = gets.to_i

arr = gets.rstrip.split(' ').map(&:to_i)

plusMinus arr
```


Input:
```
6
-4 3 -9 0 4 1         
```
Output:
```
0.500000
0.333333
0.166667
```

# diagonal-difference

https://www.hackerrank.com/challenges/diagonal-difference/problem
```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the diagonalDifference function below.

def processArray(input, rc_size)
    rc_size.collect.with_index{|num, idx| input[idx][num]}.sum
end

def diagonalDifference(a)
    len = a.length
    in_arr = (0...len).to_a
    (processArray(a, in_arr) - processArray(a, in_arr.reverse)).abs    
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

n = gets.to_i

a = Array.new(n)

n.times do |i|
    a[i] = gets.rstrip.split(' ').map(&:to_i)
end

result = diagonalDifference a

fptr.write result
fptr.write "\n"

fptr.close()
```

Input:
```
3
11 2 4
4 5 6
10 8 -12
```
Output:
```
15
```

# a-very-big-sum

https://www.hackerrank.com/challenges/a-very-big-sum/problem
```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the aVeryBigSum function below.
def aVeryBigSum(ar)
    ar.inject(&:+)
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

ar_count = gets.to_i

ar = gets.rstrip.split(' ').map(&:to_i)

result = aVeryBigSum ar

fptr.write result
fptr.write "\n"

fptr.close()
```

Input:
```
5
1000000001 1000000002 1000000003 1000000004 1000000005
```

Output:
```
5000000015
```

# compare-the-triplets

https://www.hackerrank.com/challenges/compare-the-triplets/problem
```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the solve function below.
def solve(a, b)
    res = a.collect.with_index{|aa,idx| (aa <=> b[idx])}
	res.delete(0)
    positives, negatives = res.partition(&:positive?)
  	[positives.length, negatives.length]
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

a = gets.rstrip.split(' ').map(&:to_i)

b = gets.rstrip.split(' ').map(&:to_i)

result = solve a, b

fptr.write result.join " "
fptr.write "\n"

fptr.close()

```

Input:
```
5 6 7
3 6 10
```

Output:
```
1 1 
```

# extra-long-factorials

https://www.hackerrank.com/challenges/extra-long-factorials/problem

```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the extraLongFactorials function below.
def extraLongFactorials(n)
    puts (1..n).to_a.inject(&:*)
end

n = gets.to_i

extraLongFactorials n
```

Input:
```
25
```
Output: 
```
15511210043330985984000000
```
# reduced-string

https://www.hackerrank.com/challenges/reduced-string/problem

```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the super_reduced_string function below.
def super_reduced_string(s)
    s_len = s.length
    return "Empty String" if s_len < 1
    res = ""
    s_len.times{|t|
      char = s[t]
      (res.length >= 1 && res[-1] == char) ? res.slice!(-1) : (res += char)
    }
    res != "" ? res : "Empty String"
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

s = gets.to_s.rstrip

result = super_reduced_string s

fptr.write result
fptr.write "\n"

fptr.close()

```

Input:
```
aaabccddd
```
Output: 
```
abd
```

# clock-delay

https://www.hackerrank.com/contests/hourrank-28/challenges/clock-delay/problem

```
#!/bin/ruby

require 'json'
require 'stringio'

# Complete the lagDuration function below.
def lagDuration(h1, m1, h2, m2, k)
    #t1 = Time.new(2018, 01, 01, h1, m1)
    #t2 = Time.new(2018, 01, 01, h2, m2)
    #t3 = Time.new(2018, 01, 01, (h1 + k), m1)
    #res1 = ((t1.to_i - t2.to_i).abs)/60
    #res2 = ((t1.to_i - t3.to_i).abs)/60
    #(res2 - res1)
    
    # Shortest way to do
    h = h2 - h1
    m = m2 - m1
    k * 60 - (h * 60 + m)
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

q = gets.to_i

q.times do |q_itr|
    h1M1H2M2 = gets.rstrip.split

    h1 = h1M1H2M2[0].to_i

    m1 = h1M1H2M2[1].to_i

    h2 = h1M1H2M2[2].to_i

    m2 = h1M1H2M2[3].to_i

    k = gets.to_i

    result = lagDuration h1, m1, h2, m2, k

    fptr.write result
    fptr.write "\n"
end

fptr.close()

```
Input:
```
4
21 2 21 27
2
1 57 5 34
10
18 45 19 4
5
8 55 11 12
3
```
Output:
```
95
383
281
43
```
