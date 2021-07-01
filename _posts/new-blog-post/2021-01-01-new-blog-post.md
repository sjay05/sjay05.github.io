---
layout: post
title:  "New Blog Post"
---

## Subtask 1

For each query from ~l~ to $$r$$, iterate $$r \le i \le N$$ and find the furthest left endpoint $$\text{lft}[i]$$ such that all stuffed animals from $$\text{lft}[i]$$ to $$i$$ are unique. We take the maximum of $$i - \text{lft}[i] + 1$$ for all $$\text{lft}[i] \le l$$.

**Time Complexity:** $$\mathcal{O}(Q N^2)$$

## Subtask 2

To optimize, we use a two pointer approach to determine $$\text{lft}[i]$$ for all $$r \le i \le N$$ in linear time, moving the right pointer backward only when a non-unique stuffed animal is reached and updating a count array accordingly.

As we did before, we take the maximum of $$i - \text{lft}[i] + 1$$ for all $$\text{lft}[i] \le l$$.

**Time Complexity:** $$\mathcal{O}(Q N)$$

<!-- more -->

## Subtask 3

As before, we precompute $$\text{lft}[i]$$ for all $$i$$ $$(1 \leq i \leq N)$$. By using of the monotonic property of $$\text{lft}$$, the answer for query $$l_i, r_i$$ can be found by binary searching for the right most index $$\text{pos}$$ such that $$\text{lft}[\text{pos}] \le l_i$$. All $$k > \text{pos}$$ have right endpoints higher than $$l_i$$. Thus, we only need the largest distinct subarray with right endpoint in the range $$[r_i, \text{pos}]$$. We can perform this query using a range tree like a Segment Tree or a Sparse Table.

**Time Complexity:** $$\mathcal{O}((N + Q) \log N)$$

Test in-line math: You are given $$N$$.

$$f(x) = 1$$

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight cpp %}
#include <bits/stdc++.h>

using namespace std;

int main() {
  ios::sync_with_stdio(false);
  cin.tie(0);
  int n;
  cin >> n;
  vector<int> a(n);
  for (int i = 0; i < n; i++) {
    cin >> a[i];
  }
  return 0;
}
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

