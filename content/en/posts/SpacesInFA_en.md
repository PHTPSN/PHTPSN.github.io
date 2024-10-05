---
author: "PHTPSN"
title: "Topological Properties of common Metric Spaces"
date: "2024-9-25 (A date I was once scared...)"
description: ""
tags: ["Functional Analysis"]
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

# Tables Collection

## Topological Properties of common Metric Spaces

<table align = "center">
<tbody align = "center" valign = "center">
<tr>
    <th colspan = "6">Topological Properties of common Metric Spaces</th>
</tr>
<tr>
    <th colspan = "2">Metric Space</th>
    <th>Norm</th>
    <th>Distance</th>
    <td>Separability</td>
    <td>Completeness (Banach space for normed space)</td>  
</tr>
<tr>
    <td colspan = "2">\(n\)-dimension Eucilidean space \((\mathbb{R}^n,d)\)</td>
    <td>$$\Vert x\Vert = \sqrt{\sum_{i=1}^{n} x_i^2}$$</td>
    <td>
    $$
    d(x,y) = \sqrt{\sum_{i=1}^{n} (x_i-y_i)^2}
    $$
    </td>
    <td>&#10003</td>
    <td>&#10003</td>
</tr>
<tr>
    <td rowspan = "2">Discrete metric space \((X,d_0)\)</td>
    <td>\(X\) is countable</td>
    <td rowspan = "2">/</td>
    <td rowspan = "2">$$d_0(x,y)=\begin{cases}0, x=y\\1, x\not=y\end{cases}$$</td>
    <td>&#10003</td>
    <td>&#10003</td>
</tr>
<tr>
    <td>\(X\) is uncountable</td>
    <td>&#10007</td>
    <td>&#10003</td>
</tr>
<tr>
    <td rowspan = "2" colspan = "2">Space of continuous functions  \(\mathscr{C}[a,b]\)</td>
    <td>$$\Vert f\Vert = \max\limits_{x\in [a,b]} \vert f(x)\vert$$</td>
    <td>$$d(f,g) = \max\limits_{x\in [a,b]} \vert f(x)-g(x)\vert$$</td>
    <td>&#10003</td>
    <td>&#10003</td>
</tr>
<tr>
    <td>$$\Vert f\Vert = \int_a^b \vert f(t)\vert \,\mathrm{d}x$$</td>
    <td>$$d(f,g) = \int_a^b \vert f(t)-g(t)\vert \,\mathrm{d}x$$</td>
    <td>&#10003</td>
    <td>&#10007</td>
</tr>
<tr>
    <td colspan = "2">Space of bounded sequences \(\ell^\infty\)</td>
    <td>$$\Vert x\Vert = \sup\limits_{i\geq 1} \vert x_i\vert$$</td>
    <td>$$d(x,y) = \sup\limits_{i\geq 1} \vert x_i-y_i\vert$$</td>
    <td>&#10007</td>
    <td>&#10003</td>
</tr>
<tr>
    <td colspan = "2">Variable exponent sequence space \(\ell^p\)</td>
    <td>$$\Vert x\Vert = \left(\sum_{i=1}^{\infty} \vert x_i\vert^p\right)^\frac{1}{p}$$</td>
    <td>$$d(x,y) = \left(\sum_{i=1}^{\infty} \vert x_i-y_i\vert^p\right)^\frac{1}{p}$$</td>
    <td>&#10003</td>
    <td>&#10003</td>
</tr>
<tr>
    <td colspan = "2">\(p\)-norm Lebesgue space \(L^p\)</td>
    <td>$$\Vert f\Vert = \left(\int_{[a,b]} \vert f(x)\vert^p \,\mathrm{d}x\right)^\frac{1}{p}$$</td>
    <td>$$d(f,g) = \left(\int_{[a,b]} \vert f(x)-g(x)\vert^p \,\mathrm{d}x\right)^\frac{1}{p}$$</td>
    <td>&#10003</td>
    <td>&#10003</td>
</tr>
</tbody>
</table>

</body>