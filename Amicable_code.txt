def sum_factors(n):  
     '''In this fuction, returns sum of proper divisors on n'''
     result = []
     for i in range(1, int(n**0.5) + 1):
         if n % i == 0:
             result.extend([i, n//i])
     return sum(set(result)-set([n]))

def amicable_pair(number):
    '''In this fuction, find out sum of all amicable numbers less then or equal to 1000000'''
    result = []
    for x in range(1,number+1):
        y = sum_factors(x)
        if sum_factors(y) == x and x != y:
            #sum of factor of 1st number is equal to another number. 
            result.append(tuple(sorted((x,y))))
            # find the pair of number
    return set(result)
print(amicable_pair(1000000))
