# Ruby_book_exercises.rb
Launch School 

#1. Use the each method of Array to iterate over 
#   [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], and print out each value.
array = [1, 2, 3, 4, 5, 6,  7, 8, 9, 10] 
array.each { do |x| puts x} 

#2. Same as above, but only print out values greater than 5. 
array.each do |n| 
  if n > 5
    puts n
  else
    puts "n is weak" 
  end
end 

#3. Now, using the same array from #2, use the select method
#   to extract all odd numbers into a new array. 
 array_2 = array.select { |n| n % 2 != 0} 

 #4 Append 11 to the end of the orriginal array and prepend 0 
 #  to the beggining 
 array.push(11)
 array.unshift(0)

 #5 Get rid of 11 and append 3
 array.pop
 array.unshift(3) 

 #6 get rid of duplicates without specifically removing any one value
 array.uniq! 
 
 #7 what the major difference between an array and a hash? 
 # answer: a Hash contains key value pairs that you can refernce where 
 # an array only contains the values
 
 #8 Create a Hash, with one key value pair, using both ruby syntax styles
 hash = { key: 'value'} 
 old_hash = {:key => 'value'} 

#9 suppose you have a hash h = {a: 1, b: 2, c: 3, d: 4}
# Get the value of :b, add to this hash the key:value pair {e:5}
# and remove all unknown key:value pairs whose value is less than 3.5
h = {a: 1, b: 2, c: 3, d: 4} 

h[:b] 
h[:e] = 5
h.delete_if { |key, value| value < 3.5} 

#10 Can hash values be arrays? Can you have an array of hashes?
# You can have both an array of hashes AND a hash of arrays
hash_with_arrays = {array: [1, 2, 3, 4}]} 
array_with_hashes = [{key: 'value'}, {key_2: 'value 2'}] 

#11 Look at several Rails/Ruby online documentation sources and say
#  which you like best and why 

#  I really enjoyed the code acedemy course (well actually it could be quite
#  frustrating when it would bug out and tell me i was wrong until i used 
#  the help button but, outside of that). I enjoyed the hands on approach that made  
#  me feel like i could really do something with the knowledge i had gained. But I 
#  Understand that the Launch School Course seems to be more focused on 
#  giving the students everything we need before we try to build something
#  on a larger scale so we can do it well. 

#12 Given the following data structures. Write a program that copies the information
#  from the array into the empty hash that applies to the correct person

contact_data = [["joe@email.com", "123 Main st.", "555-123-4567"],
            ["sally@email.com", "404 Not Found Dr.", "123-234-3454"]]

contacts = {"Joe Smith" => {}, "Sally Johnson" => {}}

contacts["Joe Smith"][:email] = "joe@email.com"
contacts["Joe Smith"][:address] = '123 Main st.'
contacts["Joe Smith"][:phone_number] = "555-123-4567"
contacts["Sally Johnson"][:email] = "sally@email.com"
contacts["Sally Johnson"][:address] =  "404 Not Found Dr."
contacts["Sally Johnson"][:phone_number] = "123-234-3454"

#13 Using the hash you created from the previous exercise, demonstrate how you would
#  access Joe's eamil and Sally's Phone number. 

contacts["Joe Smith"][:email] 
contacts["Sally Johnson"][:phone_number] 

#14 In exercise 12, we manually set the contacts hash values one by one. Now,
# programmatically loop or iterate over the contacts hash from exercise 12, and 
# populate the associated data from the contact_data array. Hint: you will probably
# need to iterate over ([:email, :address, :phone]), and some helpful methods might
# be the Array shift and first methods. 

contact_data = ["joe@email.com", "123 Main st.", "555-123-4567" ] 
contacts = {"Joe Smith" => {}} 
information = [:email, :address, :phone_number ] 

contacts.each do |contact, hash| 
  information.each do |info| 
    hash[info] = contact_data.shift 
  end 
end 
#watched video walkthrough for 14 
#15 Use Ruby's Array method delete.if and String method start_with? to
#  delete all of the words that begin with an "s" in the following array. 
arr = ['snow', 'winter', 'ice', 'slippery', 'salted roads', 'white trees']

arr.delete_if { |word| word.start_with?("s") } 
arr.delete_if { |words| words.start_with?("s", "w")} 

#16 take the following array and turn it into a new array that consists of 
#  strings containg one word(ex. ["white snow", etc...] => ["white", "snow"])
# Look into using Array's map and flatten methods, as well as String's split method.

a = ['white snow', 'winter wonderland', 'melting ice', 'slippery sidewalk',
 'salted roads', 'white trees'] 

array = a.map { |pairs| pairs.split } #takes the word paurs into their own arrays 
array = array.flatten                 #flattens the smaller arrays into one
p array 

#17 what will the folowing program output? 
hash1 = {shoes: "nike", "hat" => "adidas", :hoodie => true}
hash2 = {"hat" => "adidas", :shoes => "nike", hoodie: true}

if hash1 == hash2
  puts "These hashes are the same!"
else
  puts "These hashes are not the same!"
end 
#"These hashes are the same!" 
#they are just the old and new ruby syntax
