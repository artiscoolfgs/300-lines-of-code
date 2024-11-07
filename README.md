function factorial(n)
    if n == 0 then
        return 1
    else
        return n * factorial(n - 1)
    end
end

function fibonacci(n)
    if n <= 1 then
        return n
    else
        return fibonacci(n - 1) + fibonacci(n - 2)
    end
end

function randomString(length)
    local charset = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"
    local result = ""
    for i = 1, length do
        local rand = math.random(1, #charset)
        result = result .. string.sub(charset, rand, rand)
    end
    return result
end

function squareRoot(n)
    local x = n
    local y = 1
    local e = 0.000001
    while x - y > e do
        x = (x + y) / 2
        y = n / x
    end
    return x
end

function randomNumber(lower, upper)
    return math.random(lower, upper)
end

function tableSum(tbl)
    local sum = 0
    for _, v in ipairs(tbl) do
        sum = sum + v
    end
    return sum
end

function isPrime(n)
    if n <= 1 then
        return false
    end
    for i = 2, math.sqrt(n) do
        if n % i == 0 then
            return false
        end
    end
    return true
end

function generatePrimes(limit)
    local primes = {}
    for i = 2, limit do
        if isPrime(i) then
            table.insert(primes, i)
        end
    end
    return primes
end

function reverseString(str)
    local reversed = ""
    for i = #str, 1, -1 do
        reversed = reversed .. string.sub(str, i, i)
    end
    return reversed
end

function isPalindrome(str)
    return str == reverseString(str)
end

function stringLength(str)
    local length = 0
    for _ in string.gmatch(str, ".") do
        length = length + 1
    end
    return length
end

function sumOfDigits(n)
    local sum = 0
    while n > 0 do
        sum = sum + n % 10
        n = math.floor(n / 10)
    end
    return sum
end

function countdown(n)
    if n <= 0 then
        return
    else
        countdown(n - 1)
    end
end

function factorialIterative(n)
    local result = 1
    for i = 2, n do
        result = result * i
    end
    return result
end

function gcd(a, b)
    while b ~= 0 do
        a, b = b, a % b
    end
    return a
end

function lcm(a, b)
    return (a * b) / gcd(a, b)
end

function average(tbl)
    return tableSum(tbl) / #tbl
end

function randomTable(length, min, max)
    local tbl = {}
    for i = 1, length do
        table.insert(tbl, randomNumber(min, max))
    end
    return tbl
end

function binarySearch(tbl, target)
    local left, right = 1, #tbl
    while left <= right do
        local mid = math.floor((left + right) / 2)
        if tbl[mid] == target then
            return mid
        elseif tbl[mid] < target then
            left = mid + 1
        else
            right = mid - 1
        end
    end
    return -1
end

function quicksort(tbl, low, high)
    if low < high then
        local pi = partition(tbl, low, high)
        quicksort(tbl, low, pi - 1)
        quicksort(tbl, pi + 1, high)
    end
end

function partition(tbl, low, high)
    local pivot = tbl[high]
    local i = low - 1
    for j = low, high - 1 do
        if tbl[j] <= pivot then
            i = i + 1
            tbl[i], tbl[j] = tbl[j], tbl[i]
        end
    end
    tbl[i + 1], tbl[high] = tbl[high], tbl[i + 1]
    return i + 1
end

function randomMatrix(rows, cols, min, max)
    local matrix = {}
    for i = 1, rows do
        matrix[i] = {}
        for j = 1, cols do
            matrix[i][j] = randomNumber(min, max)
        end
    end
    return matrix
end

function matrixSum(matrix)
    local sum = 0
    for i = 1, #matrix do
        for j = 1, #matrix[i] do
            sum = sum + matrix[i][j]
        end
    end
    return sum
end

function matrixTranspose(matrix)
    local transposed = {}
    for i = 1, #matrix[1] do
        transposed[i] = {}
        for j = 1, #matrix do
            transposed[i][j] = matrix[j][i]
        end
    end
    return transposed
end

function factorialSequence(n)
    local sequence = {}
    for i = 1, n do
        sequence[i] = factorial(i)
    end
    return sequence
end

function stringContains(str, substring)
    return string.find(str, substring) ~= nil
end

function uniqueElements(tbl)
    local seen = {}
    local unique = {}
    for _, v in ipairs(tbl) do
        if not seen[v] then
            seen[v] = true
            table.insert(unique, v)
        end
    end
    return unique
end

function randomList(length, min, max)
    local list = {}
    for i = 1, length do
        table.insert(list, randomNumber(min, max))
    end
    return list
end

function doubleElements(tbl)
    local doubled = {}
    for _, v in ipairs(tbl) do
        table.insert(doubled, v * 2)
    end
    return doubled
end

function randomBoolean()
    return math.random() > 0.5
end

function countOccurrences(tbl, value)
    local count = 0
    for _, v in ipairs(tbl) do
        if v == value then
            count = count + 1
        end
    end
    return count
end

function maxElement(tbl)
    local max = tbl[1]
    for i = 2, #tbl do
        if tbl[i] > max then
            max = tbl[i]
        end
    end
    return max
end

function minElement(tbl)
    local min = tbl[1]
    for i = 2, #tbl do
        if tbl[i] < min then
            min = tbl[i]
        end
    end
    return min
end

function flattenTable(tbl)
    local flat = {}
    for _, v in ipairs(tbl) do
        if type(v) == "table" then
            local subFlat = flattenTable(v)
            for _, subV in ipairs(subFlat) do
                table.insert(flat, subV)
            end
        else
            table.insert(flat, v)
        end
    end
    return flat
end

function cumulativeSum(tbl)
    local result = {}
    local sum = 0
    for _, v in ipairs(tbl) do
        sum = sum + v
        table.insert(result, sum)
    end
    return result
end

function isEven(n)
    return n % 2 == 0
end

function isOdd(n)
    return n % 2 ~= 0
end

function countEvens(tbl)
    local count = 0
    for _, v in ipairs(tbl) do
        if isEven(v) then
            count = count + 1
        end
    end
    return count
end

function countOdds(tbl)
    local count = 0
    for _, v in ipairs(tbl) do
        if isOdd(v) then
            count = count + 1
        end
    end
    return count
end

function rotateList(tbl, positions)
    local len = #tbl
    positions = positions % len
    local rotated = {}
    for i = 1, len do
        rotated[i] = tbl[(i - positions - 1) % len + 1]
    end
    return rotated
end

function bubbleSort(tbl)
    local n = #tbl
    for i = 1, n - 1 do
        for j = 1, n - i do
            if tbl[j] > tbl[j + 1] then
                tbl[j], tbl[j + 1] = tbl[j + 1], tbl[j]
            end
        end
    end
    return tbl
end
