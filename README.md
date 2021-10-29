``` rb
#Split string into array
#brute force down the list join every word.length elemtents togehter and check if it is equal to word
#if equal to word add to hash 1 points
dictionary = ["below","down","go","going","horn","how","howdy","it","i","low","own","part","partner","sit"]


def substring(string, arr)
    #splis string into array
    tempArray = string.split("")
    i = 0

    #reduces arr to a Hash with default value of 0
    arr.reduce(Hash.new(0)) do |result, word|
        #iterates through temp array
        while i < tempArray.length
            #set temp variable ar to array with the elements starting tempArray[i] and ending at tempArray[wordlength + i]
            ar = tempArray[i...word.length + i]
            #if the word is equal to the temporary word we just created then add it to hash
            if (word == ar.join(""))
                then
                    result[word] += 1
            end
            #shift iteration over 1
            i += 1;
        end
        i = 0
        result
    end

    
end

s = gets.chomp
puts s
p substring(s.to_s, dictionary)
```
