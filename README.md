# i-love-you-sed

all in the repo's name


## Because 1


<div class="post-8 post type-post status-publish format-standard hentry category-faq category-linux category-sed category-shell category-tips tag-oneliners tag-sed tag-shell tag-text-processing" id="post-8">
			<h2 class="posttitle">Using different delimiters in sed</h2>
			<div class="postmetadata">
								Posted by&nbsp;<span class="postauthor"><a href="https://backreference.org/myob/myob/" title="Posts by waldner" rel="author">waldner</a></span> on								<span class="postdate">20 February 2010, 6:56 pm</span>
			</div>
			<div class="postentry">
				<p>What if, in sed, you have lots of slashes in the pattern and/or replacement?</p>
<p>One solution is to escape them all (the so-called toothsaw effect):</p>
<pre><strong>sed 's/\/a\/b\/c\//\/d\/e\/f\//'</strong>    # change "a/b/c/" to "d/e/f/"</pre>
<p>but that is ugly and unreadable. It's a not-so-known fact that sed can use any character as separator for the "s" command. Basically, sed takes whatever follows the "s" as the separator. So, our code above can be rewritten for example in one of the following ways:</p>
<pre><strong>sed 's_/a/b/c/_/d/e/f/_'
sed 's;/a/b/c/;/d/e/f/;'
sed 's#/a/b/c/#/d/e/f/#'
sed 's|/a/b/c/|/d/e/f/|'
sed 's /a/b/c/ /d/e/f/ '</strong>       # yes, even space
# etc.</pre>
<p>An even less-known fact is that you can use a different delimiter <em>even for patterns used in addresses</em>, using a special syntax:</p>
<pre># do this (ugly)...
<strong>sed '/\/a\/b\/c\//{do something;}'</strong>
# ...or these (better)
<strong>sed <span>'\#/a/b/c/#{do something;}'
sed </span><span>'\_/a/b/c/_{do something;}'
sed </span><span>'\%/a/b/c/%{do something;}'</span></strong>
# etc.</pre>
							</div>
	
			<div class="postmetadata">
				<div class="posttagscat">
								<span class="postcat">Filed under&nbsp;<a href="https://backreference.org/category/faq/" rel="category tag">faq</a>, <a href="https://backreference.org/category/linux/" rel="category tag">linux</a>, <a href="https://backreference.org/category/sed/" rel="category tag">sed</a>, <a href="https://backreference.org/category/shell/" rel="category tag">shell</a>, <a href="https://backreference.org/category/tips/" rel="category tag">tips</a></span>
								<span class="posttags">Tagged&nbsp;<a href="https://backreference.org/tag/oneliners/" rel="tag">oneliners</a>, <a href="https://backreference.org/tag/sed/" rel="tag">sed</a>, <a href="https://backreference.org/tag/shell/" rel="tag">shell</a>, <a href="https://backreference.org/tag/text-processing/" rel="tag">text processing</a></span>				</div>
				<span class="postcomment">Comments are closed								</span>
				<span class="permalink">&nbsp;|&nbsp;&nbsp;<a href="https://backreference.org/2010/02/20/using-different-delimiters-in-sed/" rel="bookmark" title="Permanent Link to Using different delimiters in sed">Permalink</a></span>
						</div>
	</div>


# Credits

* https://backreference.org/2010/02/20/using-different-delimiters-in-sed/ [Because 1](#because-1)
