There is a question which is as follows:
"Alice is playing an arcade game and wants to climb to the top of the leaderboard and wants to track her ranking. The game uses Dense Ranking, so its leaderboard works like this:
  The player with the highest score is ranked number  on the leaderboard.
  Players who have equal scores receive the same ranking number, and the next player(s) receive the immediately following ranking number.

For example, the four players on the leaderboard have high scores of 100, 90, 90, and 80. Those players will have ranks 1, 2, 2, and 3 respectively. If Alice's scores are 70, 80 and 105 her rankings after each game are 4th, 3rd  and 1st.

Function Description:
Complete the "climbingLeaderboard" function in the editor below. It should return an integer array where each element  represents Alice's rank after the jth game.
"climbingLeaderboard" has the following parameter(s):

scores: an array of integers that represent leaderboard scores
alice: an array of integers that represent Alice's scores

So I have written a function in python 3 as given below:
def climbingLeaderboard(scores, alice):
    a=len(alice)
    scores=list(dict.fromkeys(scores))
    scores.sort(reverse=True)
    for i in range(a):
        if alice[i] in scores:
            alice.append(scores.index(alice[i])+1)
            scores.remove(alice[i])
        else:
            scores.append(alice[i])
            scores.sort(reverse=True)
            alice.append(scores.index(alice[i])+1)
            del(scores[scores.index(alice[i]):])   
    return(alice[a:])

the issue with this code is it gives a timeout error for inputs with larger length. But it runs fine with the smaller inputs.

Can someone please help me how to optimize this code.
