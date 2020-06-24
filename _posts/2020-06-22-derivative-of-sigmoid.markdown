---
author: "Bipin Adhikari"
title: "Derivative of a Sigmoid Function" 
date: 2020-06-22
tags: [machine learning, mathematics, sigmoid]
excerpt: "Machine Learning , Mathematics , Sigmoid"
mathjax: "true"

---
In this post, we are going to learn indepth explanation about how the derivative of a `sigmoid function` is calculated.

Following is the representation of a `sigmoid function` :

$$
\sigma(z) = \frac{\mathrm{1}} {(\mathrm{1} + e^\mathrm{-z} )} 
$$

`Step 1`

Simplifying the equation for further process:

$$ 
\sigma'(z) = \frac{d} {dz} ( \mathrm{1} + e^\mathrm{-z} )^\mathrm{-1} 
$$ 

`Step 2`

Now , we start working with the Right Hand Side.
Matching the base and using the chain rule :

$$
\frac{d (\mathrm{1} + e^\mathrm{-z})^\mathrm{-1} } {d(\mathrm{1} + e^\mathrm{-z})} \times  \frac{d( 1 + e^\mathrm{-z} )} {d(z)}
$$

`Step 3`

Lets consider the terms on either side of multiplication sign as first term and second term.
Now , perform derivative on both the terms:

`Hints:`
* For first term , derivative of $$a^n$$  is  :
$$ 
n\times a^\mathrm{n-1}
$$
* Simplify the second term for performing derivative.

$$
-1 \times (1+ e^\mathrm{-z})^\mathrm{-1-1} \times [ \frac{d(1)}{d(z)} + \frac{d(e^\mathrm{-z})}{d(z)} ]
$$

`Step 4`

Simplifying the 1st term by arranging numerator and denominator.

For second term,

 `Hint:` Derivative of `1` is `0` .(`Since, derivative of a constant is 0`)

$$
\frac{d(e^\mathrm{-z})} {d(z)} = \frac{d(e^\mathrm{-z})} {d(\mathrm{-z})} \times \frac{d(\mathrm{-z})}{d(z)} = e^\mathrm{-z} \times -1
$$

Hence, we get the following form : 

$$
\frac{\mathrm{-1}}  { (1+e^\mathrm{-z})^\mathrm{2} } \times [0 + -e^\mathrm{-z}]
$$

`Step 5`

Simplifying the above equation :

$$
\frac{e^\mathrm{-z}} { (1 + e^\mathrm{-z})^2 }
$$

`Step 6`

Since, we know `Sigmoid` function is : 

$$
\sigma(z) = \frac{\mathrm{1}} {(\mathrm{1} + e^\mathrm{-z} )} 
$$

Hence, we can rewrite equation in `Step 5` as:

$$
\sigma(z) \times \frac{e^\mathrm{-z}} {(1 + e^\mathrm{-z})} 
$$

If you are still confused how we got this eqn, replace the value of $$\sigma(z)$$ and see how it is related to equation in step 5.

`Step 7`

Now , for further simplication of the above equation:
Add 1 and subtract 1 , which cancels out eachother .

$$
\sigma(z) \times \frac{(e^\mathrm{-z} + 1 -1)}{(1 + e^\mathrm{-z})}
$$

`Step 8`

$$
\sigma(z) \times [ \frac{(1 + e^\mathrm{-z})}{(1 + e^\mathrm{-z})}  -  \frac{1}{(1 + e^\mathrm{-z})} ]
$$

`Step 9`

Finally , replacing $$ \sigma(z) $$ in the equation again we get the final form :

$$
\sigma(z) ( 1  -  \sigma(z) )
$$

### Hence ,

The derivative of a sigmoid function is :

$$
\sigma'(z) = \sigma(z) ( 1  -  \sigma(z) )
$$

Thank you for reading the article !!!