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
