---
author: "PHTPSN"
title: "Topological Discussion of an Important Theorem in Analysis: Arzelà–Ascoli Theorem — On Compact Hausdorff Space"
date: "2024-9-25 (A date I was once scared...)"
description: "Hugo practice is the master, math content is the second."
tags: ["markdown", "html", "css", "Point Set Topology", "Functional Analysis"]
categories: ["themes", "syntax"]
series: ["Themes Guide"]
aliases: ["migrate-from-jekyl"]
cover:
  image: images/msg.png
  caption: "Generated using [OG Image Playground by Vercel](https://og-playground.vercel.app/)"
ShowToc: true
TocOpen: true
math: true
---

## First and Foremost

I wrote this post after studying point-set topology (we skipped the section devoted to metric spaces) and before studying functional analysis. And now, although only a very limited number of functional contact, it seems to be quite plain. 

## Main Text

### Introduction

The Arzelà–Ascoli theorem stands as a pivotal theorem in functional analysis. It provides a crucial link between the compactness of a function space and its properties of equicontinuity and uniform boundedness. This theorem, named after the Italian mathematicians Giuseppe Arzelà and Enrico Ascoli, has found applications in numerous areas of analysis, ranging from the existence of solutions to differential equations to complex analysis.

To understand the Arzelà–Ascoli theorem, it is essential to grasp the concept of a compact Hausdorff space. A Hausdorff space is a topological space where distinct points have disjoint neighborhoods, a fundamental property that ensures separation of points. Compactness, on the other hand, is a topological property that generalizes the notion of "closed and bounded" from Euclidean spaces to arbitrary topological spaces. Compact Hausdorff spaces, therefore, possess both the properties that ensures certain functions and sequences have convergent subsequences.

### Theorem Statement and Proof

The original form of the theorem, discussed on closed interval on real numbers, is represented as follow:

**Theorem 1. (Arzelà–Ascoli)** Consider a sequence of real-valued continuous functions defined on a closed and bounded interval \\([a,b]\\) of the real line. If there exists a subsequence \\(\\{ f_{n}\\}_{k\in \mathbb{N}}\\) that converges uniformly, the sequence has such properties:

1. _Uniformly boundedness._ \\(\exists M>0,\\, \forall n\in \mathbb{N},\\, x\in [a,b],\\, |f_n(x)|\leq M\\);
2. _Uniformly equicontinuity._ That is, \\(\forall \varepsilon > 0,\\, \exists \delta > 0,\\, \forall n\in \mathbb{N},\\, x,y\in [a,b],\\, |x-y|<\delta \Rightarrow |f(x)-f(y)|<\varepsilon\\).

The converse is also true.

Proof of this theorem is not very hard, so we omit it, as it can be cited from which of the general form we are going to talk about. Before that we should do some preparation for the topological space our theorem is based on.

**Definition 1. (ring of continuous functions)**  Let \\(X\\) be a topological space and \\(\mathscr{C}(X)\\) be the function space consisting of all continuous functions from \\(X\\) into \\(R\\).

To see \\(\mathscr{C}(X)\\) as a topological space, we define a topology from a convergence point of view as follow:

**Definition 2. (the topology induced by the uniform norm)** In a normed linear space \\(X\\), convergence of a sequence \\(\\{ x_n\\}  \\) to a point \\(x\\) is equivalent to \\(\lim\limits_{n\to \infty}||x_n-x|| = 0\\) (convergence in norm).

<br>

Now let's restate the theorem in topologicla field:

**Theorem 2. (Arzelà–Ascoli)** Let \\(X\\) be a complete metric space, \\(F\subseteq \mathscr{C}(X)\\) (the continuous mapping space on \\(X\\)). Then \\(F\\) is sequentially compact if and only if:

1. \\(F\\) is _uniformly bounded_, that is, \\(\exists M>0,\\, \forall f\in F,\\, |f|\leq M\\);
2. \\(F\\) is _uniformly equicontinuous_, that is, \\(\forall \varepsilon > 0,\\, \exists \delta > 0,\\, \forall f\in F,\\, x,y\in X,\\, d(x,y)<\delta \Rightarrow |f(x)-f(y)|<\varepsilon\\).

To transform "compactness" into a kind of structure that is easier to deal with mathematically, "net" is introduced. It's just like countably, infinitely segmenting the space. In math and real analysis, we have used this method inadvertently for a few times.

**Lemma. (Hausdorff)** \\(X\\) is a complete metric space. Then for \\(M\subseteq X\\), \\(M\\) is sequentially compact \\(\Leftrightarrow\\) \\(\forall \delta >0\\), there is a finite \\(\delta\\)-**net** of \\(M\\), i.e. \\(\exists\\) finite \\(N\subseteq X,\\, s.t.\\, \forall x\in M,\\, \exists y\in N,\\, d(x,y)<\delta\\).

"Net" is closely related to the diagonal rule. For sequence \\(\\{ x_i\\}  _{i=1}^{\infty}\subseteq A\\), we have subsequence sequence based on finite net:

- \\(\\{ x_i^{(1)}\\}  _{i=1}^{\infty} = \\{ x_i\\}  _{i=1}^{\infty}\\).
- For finite \\(\dfrac{1}{2}\\)-net \\(N_2\\), \\(\exists y_2\in N_2\\), \\(\\{ x_i^{(2)}\\}  _{i=1}^{\infty} \triangleq \\{ x\in \\{ x_i^{(1)}\\}  _{i=1}^{\infty}\mid d(x,y_2)<\dfrac{1}{2}\\}  \\) is infinite.

And so on, we got
$$
\\{ x_i^{(1)}\\}  _{i=1}^{\infty}\supseteq \\{ x_i^{(2)}\\}  _{i=1}^{\infty}\supseteq \cdots
$$

Aiming to choose one element of each subsequence to form a new subsequence, with order ensured, we extract it on the diagonal line: \\(\\{ x_i^{(i)}\\}  _{i=1}^{\infty}\\). Because
$$
\forall k>0,\\, \forall m,n>k,\\, d(x_k^{(m)},x_k^{(n)})\leq d(x_k^{(m)},y_k) + d(x_k^{(n)},y_k)<\dfrac{2}{k}
$$

\\(d(x_k^{(m)},x_k^{(n)})<\dfrac{2}{k}\\). Therefore \\(\\{ x_i^{(i)}\\}  _{i=1}^{\infty}\\) is Cauchy sequence, which is a convergent subsequence of \\(\\{ x_i\\}  _{i=1}^{\infty}\\).

In essence, net is a promotion of limit. For topological space \\(X\\), a net is a mapping from a directed set \\(D\\) into \\(X\\). A net \\((x_i)_{i\in D}\\) is called converging to \\(x\in X\\) when and only when \\(\forall\\) neibourhood \\(U\\) of \\(x\\), \\(\exists I\in D,\\, \forall i\geq I, x_i\in U\\). A directed set is, a preordered set \\((D,\leq)\\) which satisfies that \\(\forall i,j\in D,\\, \exists k\in D,\\, s.t.\\, i\leq k,j\leq k\\).

_Proof._ Necessity. Through a finite \\(\delta\\)-net, uniformly boundedness is obvious.

For uniformly equicontinuity, \\(\forall \varepsilon > 0\\), make use of \\(\dfrac{\varepsilon}{3}\\)-net \\(N_{\varepsilon}\\). \\(\forall g\in N_{\varepsilon}\\), \\(|f(x)-g(x)|\leq \varepsilon\\). Observing that 
$$
|f(x)-f(y)|\leq |f(x)-g(x)|+|f(y)-g(y)|+|g(x)-g(y)|<\dfrac{2}{3}\varepsilon + |g(x)-g(y)|
$$

As there are only finite \\(g\\)s, \\(\exists \delta > 0,\\, s.t.\\) \\(|g(x)-g(y)|\\) is sufficiently small. Therefore uniformly equicontinuity is proved.

Sufficiency. Conversely, \\(\forall \varepsilon > 0\\), we could find a finite \\(\delta\\)-net \\(N_\varepsilon\\) that
$$
\forall f\in F,\\, x,y\in X,\\, d(x,y)<\delta \Rightarrow |f(x)-f(y)|<\dfrac{\varepsilon}{3}
$$

Consider the mapping
$$
T:F\longrightarrow \mathbb{R}^{|N_\varepsilon|}\qquad f\longmapsto (f(n))_{n\in N}
$$

Obviously, \\(\textup{Im}T\\) is bounded. Account for the sequencial compactness of \\(\mathbb{R}^{|N_\varepsilon|}\\)'s bounded subset, we have \\(\dfrac{\varepsilon}{3}\\)-net, denoted as \\(\\{ Tf_1,\cdots,Tf_m\\}  \\). Then \\(\forall f\in F,\\, |f(x)-g(x)|<\varepsilon\\). Q.E.D.

As we can see, it is a common technique to transform the distance between two points in the space to be considered into a more easily examined distance between two points in the space to be considered, and the distance between the two points in the space to be considered, by a reduction method similar to the triangle inequality (actually a "quadrilateral").

### Promotion

The condition of the theorm could be weakened. Here we list two directions of the promotion:

1. Onto non-compact metric space.
2. Onto discontinuous mapping.

### Application Example: ODE

Any thoughtful student of mathematics should have an idea of the extensibility of **the existence and uniqueness of solutions to ordinary differential equations** when first exposed to it, which seems so ingenious that it seems like a small application of a broader conclusion.

Actually, **Lipchitz condition**
$$
\exists L, \forall n, \forall x,y\in [a,b], |f_n(x)-f_n(y)|\leq L|x-y|
$$

is a direct result of uniform boundedness of the derivatives, letting \\(L=\sup{f'_n(x)}\\). So in addition, given \\(\varepsilon > 0\\), let \\(\delta = \dfrac{\varepsilon}{2L}\\) to verify equicontinuity, the conclusion of the theorem is apparent.

### Conclusion

From the discussion above, we have got a deeper understanding of the concept "convergence" in foundational analysis, and built a bridge between compact Hausdorff spaces, the very basic topological concept, and the analytical properties of function spaces.
The importance of the Arzelà–Ascoli theorem lies in its wide-ranging applications. It is a crucial ingredient in the proof of the Peano existence theorem for solutions to ordinary differential equations. It also plays a vital role in the proof of Montel's theorem in complex analysis. Furthermore, the theorem has found applications in areas such as approximation theory, functional equations, and the study of integral equations. Its depth and breadth of applications have made it a cornerstone of modern analysis.

### Reference

[1] Ascoli, G., "Le curve limite di una varietà data di curve", Atti della R. Accad. Dei Lincei Memorie della Cl. Sci. Fis. Mat. Nat., 18 (3): 521–586  
[2] Dunford, Nelson; Schwartz, Jacob T. (1958), Linear operators, volume 1, Wiley-Interscience  
[3] James R. Munkres. Topology: a first course[M]. Englewood Cliffs: Prentice-Hal, Inc., 1975