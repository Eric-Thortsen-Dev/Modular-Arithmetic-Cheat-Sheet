# Modular Arithmetic Cheat Sheet

A reference for useful modular arithmetic formulas, including extensions to real, negative, imaginary, and complex numbers.

[![Clock Modular Arithmetic](media/clock.png)](media/clock.png)

## Definitions & Floor/Ceil Relations
The modulo operator is intimately related to the floor and ceiling functions. These definitions hold for real numbers.

*   **Standard Definition (Knuth's floored division):**
    $$a \bmod m = a - m \lfloor a/m \rfloor$$

*   **Alternative (Ceiling) Definition:**
    $$a \bmod m = a + m \lceil -a/m \rceil$$

*   **Floor/Ceil Reflection:**
    $$\lfloor a \rfloor = -\lceil -a \rceil$$
    $$\lceil a \rceil = -\lfloor -a \rfloor$$

## Negative Numbers
Derived from the floor/ceil definitions, these describe behavior when the dividend or divisor is negative.

*   **Negative Dividend:**
    $$-a \bmod m = m \lceil a/m \rceil - a$$
    *(Result is &ge; 0)*

*   **Negative Divisor:**
    $$a \bmod{-m} = a - m \lceil a/m \rceil$$
    *(Result is &le; 0)*

*   **Negative Dividend & Divisor:**
    $$-a \bmod{-m} = m \lfloor a/m \rfloor - a$$
    *(Result is &le; 0)*

## Algebraic Properties

### Addition
Modular addition distributes over the sum.
*   **For real numbers $a, b$:**
    $$(a + b) \bmod m = ((a \bmod m) + (b \bmod m)) \bmod m$$

### Multiplication
Modular multiplication distributes over the product.

*   **For Integers $a, b$:**
    $$ab \bmod m = ((a \bmod m)(b \bmod m)) \bmod m$$

*   **For Real $a$, Integer $b$:**
    $$ab \bmod m = ((a \bmod m)b) \bmod m$$

### Scaling Property (Homogeneity)
Often useful for fixed-point arithmetic or changing precision. For real numbers $x \neq 0$:

$$a \bmod m = \frac{(ax) \bmod (mx)}{x}$$

$$a \bmod m = x \left(\frac{a}{x} \bmod \frac{m}{x}\right)$$

## Complex Numbers (Component-wise)
If we define the floor of a complex number component-wise ($\lfloor x + iy \rfloor = \lfloor x \rfloor + i\lfloor y \rfloor$), the modulo operator extends naturally:

$$(a + bi) \bmod m = (a \bmod m) + (b \bmod m)i$$

## References

**General & Definitions**
*   Donald E. Knuth, *The Art of Computer Programming, Vol 1*. Addison-Wesley, 1972.
*   [Wikipedia: Modular Arithmetic](https://en.wikipedia.org/wiki/Modular_arithmetic)
*   [Norayr: Division and Modulus](http://norayr.am/papers/divmodnote.pdf)

**Scaling Property (Modulus Conversion)**
*   Graham, Knuth, & Patashnik, *Concrete Mathematics*, Chapter 3 (Integer Functions).

**Algebraic Rules**
*   [Khan Academy: Modular Multiplication](https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/modular-multiplication)
*   [Math StackExchange: Algebra with Modular Real Numbers](https://math.stackexchange.com/questions/55297/what-are-the-rules-for-basic-algebra-when-modulo-real-numbers-are-involved)
