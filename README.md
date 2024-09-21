<p align="left">
$$
\begin{align*}
text{precision, extraction\_params (midpoint, midpoint\_value), digits} := \dots \\
\text{digits} \gets \text{batch size} * (\text{stagger} + 1) \\
\text{assign A, batch size, stagger, precision} \\
\text{.indicator\_vars} := \begin{bmatrix}\text{base}^{\ceil{\frac{\text{digits}}{2}} - \text{stagger}} & \text{base}^{\ceil{\frac{\text{digits}}{2}} - 2*\text{stagger}} & \hdots & \text{base}^{-\floor{\frac{\text{digits}} {2}}}\end{bmatrix} \\
\text{.real\_vals} := \begin{bmatrix} \hdots \end{bmatrix} \\
\text{map} := \text{\{symbols} \rightarrow \text{random\_reals\}} \\
\text{coeffs} := \text{{[]}} \\
\end{align*}
$$
</p>
