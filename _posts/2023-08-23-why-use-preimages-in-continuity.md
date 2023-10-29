---
layout: post
author: funkyfunctors
published: true
use_math: true
comments: true
categories: [mathematics]
tags: [topology, analysis]
---

While studying topology, one come across a definition of continuity between spaces which goes like "Let $X$ and $Y$ be topological spaces. A function $f: X \rightarrow Y$ is said to be continuous at $x \in X$ if for any open set $V$ of $Y$ containing $f(x)$, we have $f^{-1} (V)$  to be open in $X$". While this definition holds true, its rationale might not be immediately apparent. In this post, we will delve into why preimages are favored over images, and why a simpler image-based definition falls short. 

# Notations: 

To begin, let's first establish the notation used. We consider topological spaces $X$ and $Y$, and a mapping $f: X \rightarrow Y$. Open sets of $Y$ are denoted as $V$, while open sets of $X$ are referred to as $U$. 

# Intuition of continuity and open sets: 

Before delving into the specifics, I want to discuss a bit about the intuition behind continuity and open sets. Essentially, continuity (at $x$) means all points which are infinitely close to $x$ get mapped to points infinitely close to $f(x)$. In analysis, we try to formalize this idea using 'arbitrary closeness'. For example, one might have seen the epsilon-delta definition of continuity which goes like $\forall \varepsilon>0 \cdots \vert f(x)-f(c) \vert <\varepsilon$, this statement says that however closely you look at $f(c)$, you will always find $f(x)$ for some $x$, or in other words, you can get arbitrarily close to $f(c)$. Furthermore, if $d$ is infinitely close to $x$ then $d$ would in all open intervals of $x$ because we have $\vert x-d \vert <\varepsilon$ for every $\varepsilon \in \mathbb{R}^+$. This in turn means that $d \in (x-\varepsilon, x+\varepsilon)$ for every positive $\varepsilon$. Thus, $d$ is in every open interval containing $x$ and since in reals, open set is just arbitrary union of open intervals, we might as well say that $d$ is in every open set containing $x$. One of the primary reason we reframe it in terms of open set is to get rid of metric (distance function), so that we can easily generalize it to spaces not having any well defined or interesting notion of distance. 

# Why image condition is weak:

Imagine replacing the preimage condition with the image condition: "If $U$ is an open set in $X$, then $f(U)$ is an open set in $Y$." At first glance, this might seem reasonable for defining continuity. However, upon closer examination, its insufficiency becomes evident. Consider two points, $x$ and $c$, infinitely close in $X$. This means that $c$ lies within every open set in $X$ that contains $x$. Let $U$ be one such set. Our condition asserts that $f(U)$ is open in Y. So far, so good. But now what? We know that $f(c)$ is in _some_ of open sets in $Y$ containing $f(x)$. More specifically, the open sets corresponding to open set in $X$ that includes both $x$ and $c$. However, this information is not enough to conclude that $f(x)$ and $f(c)$ are infinitely close (or in other words, that $f$ is continuous at $x$). To establish this, it's not sufficient for $f(c)$ to just be in _some_ open set around $f(x)$. Instead, it must be in _every_ open set of $Y$ that encompasses $f(x)$, not just a select few. 

# Why preimage definition works:

The essence of continuity is more accurately encapsulated through the preimage-based definition: "For any open set $V$ in $Y$ containing $f(x)$, the preimage $f^{-1}(V)$ is open in $X$." I hope you can see what is coming up, we are already talking about every open set containing $f(x)$. This definition is indeed strong enough to conclude $f(x)$ and $f(c)$ is infinitely close. Here is why. Let's say they are not. Then there must exist some open set, $V$, of $Y$ containing $f(x)$ but not $f(c)$ (because if $f(c)$ is contained in all such open set, $f(x)$ and $f(c)$ must be infact infinitely close). But that would mean $f^{-1}(V)$ is open in $X$ and does not contain $c$, that is, $x$ and $c$ are not infinitely close. A contradiction! 

# Some closing remarks: 

In conclusion, the preimage-based definition of continuity possesses robustness that the image-based condition lacks. This robustness ensures that all points infinitely close to $x$ are mapped to points infinitely close to $f(x)$, securing the foundation of continuity within the realm of topological spaces. It is worth noting that preimages are well behaved in general, as evident from properties like $f^{-1}(Y \cap Z) = f^{-1}(Y) \cap f^{-1}(Z)$, $f^{-1}(Y \cup Z) = f^{-1}(Y) \cup f^{-1}(Z)$, $f^{-1}(Y \setminus Z) = f^{-1}(Y) \setminus f^{-1}(Z)$ and other similar relationships. Perhaps, this is another reason why usage of preimage is (pre)dominant. 
