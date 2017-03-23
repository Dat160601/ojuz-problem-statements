The cows are experimenting with secret codes, and have devised a method for
creating an infinite-length string to be used as part of one of their codes.

Given a string $s$, let $F(s)$ be $s$ followed by $s$ "rotated" one character to
the right (in a right rotation, the last character of $s$ rotates around and
becomes the new first character).  Given an initial string $s$, the cows build
their infinite-length code string by repeatedly applying $F$; each step
therefore doubles the length of the current string.

Given the initial string and an index $N$, please help the cows compute the
character at the $N$th position within the infinite code string.

<div class='prob-in-spec'><h4>INPUT FORMAT (file cowcode.in):</h4>
The input consists of a single line containing a string followed by $N$.  The
string consists of at most 30 uppercase characters, and $N \leq 10^{18}$.

Note that $N$ may be too large to fit into a standard 32-bit integer, so you may
want to use a 64-bit integer type (e.g., a "long long" in C/C++).
</div>

<div class='prob-out-spec'><h4>OUTPUT FORMAT (file cowcode.out):</h4>
Please output the $N$th character of the infinite code built from the initial
string.  The first character is $N=1$.
</div>

<h4>SAMPLE INPUT:</h4><pre class='in'>
COW 8
</pre><h4>SAMPLE OUTPUT:</h4> <pre class='out'>
C
</pre>

In this example, the initial string COW expands as follows:
<pre>
COW -&gt; COWWCO -&gt; COWWCOOCOWWC
                 12345678
</pre>


Problem credits: Brian Dean