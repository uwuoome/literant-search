<h1>Word Search for Scrabble-Like Games. </h1>

Call aiInit once on startup passing a word list as an array. Word list words must be in upper case. The compress option will turn the lookup Trie into a compressed directed acyclic word graph. 
This uses less RAM, but does come with a precalc cost and doesn't affect the search speed.   
<code>aiInit(wordList, options={compress: true, debug: 0})</code>

During an AI turn call aiFindMove to search the board for the highest scoring move. The parameter board is a one dimensional array of characters. 
Empty slots are represented by spaces, capitalized letters denote placed letters and lower case letters symbolize blank tiles placed. 
The second argument, letters, is an upper-case string containing letters in the AI player's rack. For blank letters, use underscores.  
<code>aiFindMove(board, letters)</code>

Return value is an object with the following attributes:
<pre>
pos: 0...223 (one dimensional index). 
dir: "a" | "d" (across or down)
word: string  (word to place)
score: number
</pre>
