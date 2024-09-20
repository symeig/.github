# symeig: an organization based around retrieving spectral information quickly

(note to abe: trying to make a read me for the whole organization here. might need some fenaggling to get it right)

\begin{algorithm}[H]
\begin{algorithmic}
\STATE $\text{A, symbols, batch\_size, base, stagger} := \hdots$
\STATE $\text{precision, extraction\_params (midpoint, midpoint\_value), digits} := \hdots$
% \STATE $\text{digits} \gets \text{batch size} * (\text{stagger} + 1)$
%assign A, batch size, stagger, precision (batch size + 10)
\STATE $.\text{indicator\_vars} := \begin{bmatrix}\text{base}^{\ceil{\frac{\text{digits}}{2}} - \text{stagger}} & \text{base}^{\ceil{\frac{\text{digits}}{2}} - 2*\text{stagger}} & \hdots & \text{base}^{-\floor{\frac{\text{digits}} {2}}}\end{bmatrix}$
\STATE $.\text{real\_vals} := \begin{bmatrix} \hdots \end{bmatrix}$
\STATE $\text{map} := \text{\{symbols} \rightarrow \text{random\_reals\}}$
\STATE $\text{coeffs} := \text{{[]}}$

\FOR{$i=1$ to \text{num\_batches}}
\STATE $\text{map\_curr} := \text{map.copy()}$
\STATE $\text{map\_curr{[}}i*\text{batch size}, \min{\text{(n}, (i+1)*\text{batch\_size)}}\text{{]}} \mathrel{+}= \text{exp\_vars}$
\STATE $\text{A}_{i} := \text{map curr(A)}$
\STATE $\sigma := eig(\text{A}_{i}) + \text{midpoint}$
%need to modify here or switch to vectorizing by rows
\STATE $\text{coeffs.insert({[}} digits(\sigma_{j}\text{)} - \text{midpoint\_value for j in range(n){]})}$
\ENDFOR
% %rows is batch, columns is eigenvalue. concatenate eigenvalues across batches
%rewrite as mapping vec on entries?
\STATE $\text{coeffs} := \begin{bmatrix} vec\text{(coeffs[:},0\text{{]})} \\ \hdots \\ vec\text{(coeffs[:},n-1\text{{]})} \end{bmatrix}$
% calculate eigenvalues for each batch
%     -assign variables for given batch
%     -compute numeric eigenvalues
%     -midpoint_normalized_eigens = [mp.im(i)+midpoint for i in eigenvalues]
%     -return [int(i) - midpoint_value for i in val]

\end{algorithmic}
\caption{$\lambda$ solver}
\label{alg:seq}
\end{algorithm}

