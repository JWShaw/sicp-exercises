# Exercise 1.13

Given $\phi = (1 + \sqrt{5})/2$ and $\psi = (1 - \sqrt{5})/2$, we want to prove that $\text{Fib}(n)$ is the closest integer to $\phi^n/\sqrt{5}$.

It is straightforward, and will be left as an exercise, to show the following identities:

* $\phi = (1 - \psi)$
* $\psi = (1 - \phi)$
* $\phi = (-\psi^{-1})$
* $\psi = (-\phi^{-1})$
* $-\phi\psi = 1$

We start by showing that $\text{Fib}(n) = \frac{\phi^n - \psi^n}{\sqrt{5}}$ for every natural number $n$.

* Base case $n=0$: $\frac{\phi^0 - \psi^0}{\sqrt{5}} = \frac{1 - 1}{\sqrt{5}} = 0 = \text{Fib}(0)$
* Base case $n=1$: $\frac{\phi - \psi}{\sqrt{5}} = \frac{1 + \sqrt{5} - 1 + \sqrt{5}}{\sqrt{5}} = \frac{2\sqrt{5}}{2\sqrt{5}} = 1 = \text{Fib}(1)$

Suppose that $\text{Fib}(n-1)=\frac{\phi^{n-1}-\psi^{n-1}}{\sqrt{5}}$ and $\text{Fib}(n)=\frac{\phi^{n}-\psi^{n}}{\sqrt{5}}$ for some natural number $n$.

Then
\begin{align*}
  \text{Fib}(n+1) &= \text{Fib}(n) + \text{Fib}(n-1) \\
                  &= \frac{\phi^{n-1}-\psi^{n-1}}{\sqrt{5}} + \frac{\phi^{n}-\psi^{n}}{\sqrt{5}} \\
                  &= \frac{\phi^{n+1}(\phi^{-1} + \phi^{-2})-\psi^{n+1}(\psi^{-1} + \psi^{-2})}{\sqrt{5}} \\
\end{align*} 
Let us prove that $\frac{\phi^{n+1}(\phi^{-1} + \phi^{-2})-\psi^{n+1}(\psi^{-1} + \psi^{-2})}{\sqrt{5}} = \frac{\phi^{n+1}-\psi^{n+1}}{\sqrt{5}}$ by showing that $(\phi^{-1}+\phi^{-2}) = (\psi^{-1}+\psi^{-2}) = 1.$
Using the identites mentioned earlier, we find that 
\begin{align*}
\phi^{-1} + \phi^{-2} &= (-\psi)+\psi^2 \\
                      &= \psi(\psi - 1) \\
                      &= \psi(-\phi)A \\
                      &= -\phi\psi = 1 \\
                      &= \phi(-\psi) \\
                      &= \phi(\phi - 1) \\
                      &= \phi^2 - \phi \\
                      &= \psi^{-2} + \psi^{-1}
\end{align*}
Thus $\frac{\phi^{n+1}(\phi^{-1} + \phi^{-2})-\psi^{n+1}(\psi^{-1} + \psi^{-2})}{\sqrt{5}} = \frac{\phi^{n+1}-\psi^{n+1}}{\sqrt{5}} = \text{Fib}(n+1)$.
We now build up an inequality by noticing that

\begin{align*}
-1 < \psi < 0 &\iff -1 < \psi^n < 1 \\
              &\iff -1 < -\psi^n < 1 \\
              &\iff \frac{-1}{\sqrt{5}} < \frac{-\psi^n}{\sqrt{5}} < \frac{1}{\sqrt{5}} \\
              &\iff \frac{\phi^n}{\sqrt{5}} - \frac{1}{\sqrt{5}} < \frac{\phi^n - \psi^n}{\sqrt{5}} < \frac{\phi^n}{\sqrt{5}} + \frac{1}{\sqrt{5}} \\
              &\iff \frac{\phi^n}{\sqrt{5}} - \frac{1}{\sqrt{5}} < \text{Fib}(n) < \frac{\phi^n}{\sqrt{5}} + \frac{1}{\sqrt{5}} \\
              &\iff \frac{\phi^n}{\sqrt{5}} - \frac{1}{2} < \text{Fib}(n) < \frac{\phi^n}{\sqrt{5}} + \frac{1}{2} \\
\end{align*}
Thus we have shown that $\text{Fib}(n)$ is the single integer within the open interval of diameter $1/2$ centered at $\phi^n/\sqrt{5}$. $\blacksquare$
