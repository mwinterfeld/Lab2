#######################
# Part1: Hello World
#######################

class HelloWorldClass
	def initialize(name)
		@name = name.capitalize
	end
	def sayHi
		puts "Hello #{@name}!"
	end
end
puts("Part 1:")
hello = HelloWorldClass.new("Mike")
hello.sayHi
puts("\n")

#########################
# Part2: Palindromes
##########################

def palindrome?(string)
	reverse = string.each_char.to_a.reverse.join
	if(string == reverse)
		puts(string + " is a palindrome.")
	else
		puts(string + " is not a palindrome.")
	end
end

puts("Part 2:")
palindrome?("racecarsss")
palindrome?("racecar")

################################
# Part 3: Rock Paper Scissors
################################

puts("\nPart 3:")

# Exceptions
class WrongNumberOfPlayersError <  StandardError ; end
class NoSuchStrategyError <  StandardError ; end
class TieError < StandardError ; end

# Returns the winner of a single game
def rps_game_winner(game)
	raise WrongNumberOfPlayersError unless game.length == 2
	hand_space = ["R", "P", "S", "r", "p", "s"]
	hand1 = game[0][1]
	hand2 = game[1][1]
	if(!(hand_space.include?(hand1)) || !(hand_space.include?(hand2)))
		raise NoSuchStrategyError
	end

	case hand1
	when "R"
		if(hand2 == ("R" || "r"))
			raise TieError
		elsif(hand2 == ("P" || "p"))
			return game[1]
		else
			return game[0]
		end
	when "P"
		if(hand2 == ("P" || "p"))
			raise TieError
		elsif(hand2 == ("S" || "s"))
			return game[1]
		else
			return game[0]
		end
	when "S"
		if(hand2 == ("S" || "s"))
			raise TieError
		elsif(hand2 == ("R" || "r"))
			return game[1]
		else
			return game[0]
		end
	when "r"
		if(hand2 == ("R" || "r"))
			raise TieError
		elsif(hand2 == ("P" || "p"))
			return game[1]
		else
			return game[0]
		end
	when "p"
		if(hand2 == ("P" || "p"))
			raise TieError
		elsif(hand2 == ("S" || "s"))
			return game[1]
		else
			return game[0]
		end
	when "s"
		if(hand2 == ("S" || "s"))
			raise TieError
		elsif(hand2 == ("R" || "r"))
			return game[1]
		else
			return game[0]
		end
	end

end

# Finds the depth of an array 'a'
def depth(a)
	return 0 unless a.is_a?(Array)
	return 1 + depth(a[0])
end

# Returns the winner of a tournament stored as a multidimensional array
def rps_tournament_player(tournament)
	if(depth(tournament) == 2)
		left = tournament[0]
		right = tournament[1]
	else
		left = rps_tournament_player(tournament[0])
		right = rps_tournament_player(tournament[1])
	end
	
	return rps_game_winner([left, right])	
end

tournament = [
    [
        [ ["Armando", "P"], ["Dave", "S"] ],
        [ ["Richard", "R"],  ["Michael", "S"] ],
    ],
    [
        [ ["Allen", "S"], ["Omer", "P"] ],
        [ ["David E.", "R"], ["Richard X.", "P"] ]
    ]
]

winner = rps_tournament_player(tournament)
puts("The winner is: " + winner[0] + " who played " + winner[1])
p winner

########################
# Part 4: Anagrams
########################

puts("\nPart 4:")

def anagram_check(standard, test)
	standard1 = standard.downcase.chars.sort.join
	test1 = test.downcase.chars.sort.join
	if(standard1 == test1) then
		return true;
	else
		return false;
	end
end

def combine_anagrams(words)
	anagrams = []
	for w in words
		placed = false
		for s in anagrams
			if(anagram_check(s[0],w)) then 
			  s << w 
			  placed = true
			end
		end
		if(!placed) then anagrams << Array[w] end
	end
	p anagrams
end

input = ['cars', 'for', 'potatoes', 'racs', 'four', 'scar', 'creams', 'scream'] 
combine_anagrams(input)
