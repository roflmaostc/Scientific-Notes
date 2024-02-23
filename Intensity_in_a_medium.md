# Intensity
An scalar eletrical wave is given by

$$E = A \cdot \exp(i \cdot \phi)$$

Where $A$ has the units of $\mathrm{V/m}$.
Quite often people refer the intensity as $I \sim |E|^2$ but more precisely, the intensity is given by

$$I =\frac12  c \cdot n \cdot \epsilon_0 \cdot |E|^2$$

where $c$ is the speed of light in $\mathrm{m/s}$, $n$ is the refractive index in a medium and $\epsilon_0 = 8.854 \cdot 10^{−12} \mathrm{Fm^-1}$.
The units of $[I] = J / m^2 / s$ so this is a physical power. 

## Paradoxon
Using that equation naively, would mean that a beam propagating in a medium with $n>1$, the intensity is higher than in vacuum? This contradicts energy conservation.
How to solve it?

## Solution
Let's consider the situation, that a beam $E_i$ hits a interface surface.
So there will be a certain field propagation inside the medium $n_2$ $E_t$ and one in medium $n_1$ which is reflected ($E_r$).
```
medium n1     | medium n2
               |
               |
      Ei ---->|---->Et
      <-----Er|
               |
```

According to energy conservation, we have to expect $I_i = I_t + I_r$ for the beam intensities.
How to we obtain $I_t$?
Simply use $I_t = \frac12 c \cdot n_1 \cdot \epsilon_0 |E_t|^2$.
How do we obtain $E_t?$ 
Simply using the [complex Fresnel coeffients](https://en.wikipedia.org/wiki/Fresnel_equations#Complex_amplitude_reflection_and_transmission_coefficients).
Restricting ourselves to $s$ polarization and $\theta_i = 0$
$r_s = \frac{n_1 - n_2}{n_1 + n_2}$.
$t_s = \frac{2n_1}{n_1 + n_2}$.

Hence we obtain:

$$E_r = E_i \cdot \frac{n_1 - n_2}{n_1 + n_2}$$

and

$$E_t = E_i \frac{2n_1}{n_1 + n_2}$$

Adding now the intensities we get:

$$\frac12  c \cdot n_1 \cdot \epsilon_0 |E_i|^2  = \frac12  c \cdot n_1 \cdot \epsilon_0  |E_r|^2  + \frac12  c \cdot n_2 \cdot \epsilon_0 |E_t|^2$$

$$n_1 |E_i|^2  = n_1  |r_s \cdot E_i|^2  + n_2 |t_s\cdot E_i|^2$$

$$n_1 = n_1 \frac{n_1^2 + n_2^2 - 2\cdot n_1 \cdot n_2}{(n_1 + n_2)^2} + n_2 \frac{4\cdot n_1^2}{(n_1 + n_2)^2}$$


$$1 = 1 \frac{n_1^2 + n_2^2 - 2\cdot n_1 \cdot n_2 + 4\cdot n_1^2}{(n_1 + n_2)^2} $$

$$1 = 1 \frac{n_1^2 + n_2^2 + 2\cdot n_1 \cdot n_2}{(n_1 + n_2)^2} $$

Now both sides are equivalent.
So the take home messages. Such that the energy balances really work out, you have to use the proper intensity definition and not only $|E|^2$. It is easy to forget some scaling factors because of the refractive indices.
