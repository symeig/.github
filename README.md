like in $1(23)4$  
like in $\pi$  

$\text{precision, extractionparams midpoint, midpointvalue, digits} \gets \dots$  
$\text{digits} \gets \text{batchsize}\*\(\text{stagger}+1\)$  
$\text{indicatorvars} = \[\text{base}^{\lceil \frac{\text{digits}}{2} \rceil - \text{stagger}} \\; \text{base}^{\lceil \frac{\text{digits}}{2} \rceil - 2*\text{stagger}} \\; \dots \\; \text{base}^{-\lfloor \frac{\text{digits}}{2} \rfloor}\]$   
assign A, batch size, stagger, precision  
$\text{realvals} \gets \[ \dots \]$  
$\text{map} \gets \\{\text{symbols} \rightarrow \text{randomreals}\\}$  
$\text{coeffs} := \[\]$  
for \(i=1 to numbatches\):  
&nbsp;&nbsp;&nbsp;&nbsp; mapcurr $:=\text{map.copy()}$  
&nbsp;&nbsp;&nbsp;&nbsp; mapcurr $\[i*\text{batchsize}, \min{\(\text{n}, \(i+1\)\*\text{batchsize}\)}\] +\!\!\! = \text{expvars}$  
&nbsp;&nbsp;&nbsp;&nbsp; $A_{i} := \text{mapcurr(A)}$  
&nbsp;&nbsp;&nbsp;&nbsp; $\sigma$  
&nbsp;&nbsp;&nbsp;&nbsp; $\sigma := eig(A_{i}) + \text{midpoint}$  
$\begin{array}{cc} a & b \\\\ c & d \\end{array}$  

\text{coeffs.insert({[}} digits(\sigma_{j}\text{)} - \text{midpoint\_value for j in range(n){]})}$
\ENDFOR
% %rows is batch, columns is eigenvalue. concatenate eigenvalues across batches
%rewrite as mapping vec on entries?
\STATE $\text{coeffs} := \begin{bmatrix} vec\text{(coeffs[:},0\text{{]})} \\ \hdots \\ vec\text{(coeffs[:},n-1\text{{]})} \end{bmatrix}$

