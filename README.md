like in $1(23)4$  
like in $\pi$  

$\text{precision}$, extraction_params midpoint, midpoint_value, digits $\gets \dots$  
$digits \gets \text{batchsize}\*\(\text{stagger}+1\)$  
indicatorvars $= \[\text{base}^{\lceil \frac{\text{digits}}{2} \rceil - \text{stagger}} \\; \text{base}^{\lceil \frac{\text{digits}}{2} \rceil - 2*\text{stagger}} \\; \dots \\; \text{base}^{-\lfloor \frac{\text{digits}}{2} \rfloor}\]$   
assign A, batch size, stagger, precision  
.real_vals $\gets \[ \dots \]$  
map $\gets \\{\text{symbols} \rightarrow \text{randomreals}\\}$  
coeffs $:= \[\]$  
for \(i=1 to numbatches\):  
&nbsp;&nbsp;&nbsp;&nbsp; mapcurr $:=\text{map.copy()}$  
&nbsp;&nbsp;&nbsp;&nbsp; mapcurr $\[i*\text{batchsize}, \min{\(\text{n}, \(i+1\)\*\text{batchsize}\)}\] +\!\!\! = \text{expvars}$  
&nbsp;&nbsp;&nbsp;&nbsp; A $_{i} := \text{mapcurr(A)}$  
&nbsp;&nbsp;&nbsp;&nbsp; $\sigma$  
&nbsp;&nbsp;&nbsp;&nbsp; $\text{A}_{i}$  
&nbsp;&nbsp;&nbsp;&nbsp; $A_{i}$    
&nbsp;&nbsp;&nbsp;&nbsp; $\sigma := eig(\text{A}_{i}) + \text{midpoint}$

