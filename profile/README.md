# symeig: retrieving spectral information quickly
(public view from .github repo)  
$\text{eig\(}A\text{, batchsize, stagger\): }$    
&nbsp;&nbsp;&nbsp;&nbsp; $n\text{, midpoint, midpointvalue, symbols} := \dots$  
&nbsp;&nbsp;&nbsp;&nbsp; $\text{digits} := \text{batchsize}\*\(\text{stagger}+1\)$  
&nbsp;&nbsp;&nbsp;&nbsp; $\text{indicatorvars} := \[\text{base}^{\lceil \frac{\text{digits}}{2} \rceil - \text{stagger}}, \\; \text{base}^{\lceil \frac{\text{digits}}{2} \rceil - 2*\text{stagger}}, \\; \dots, \\; \text{base}^{-\lfloor \frac{\text{digits}}{2} \rfloor}\]$    
&nbsp;&nbsp;&nbsp;&nbsp; $\text{map} := \\{\text{symbols } \: \text{ randomreals}\\}$  
&nbsp;&nbsp;&nbsp;&nbsp; $\text{coeffs} := \[\]$  
  
&nbsp;&nbsp;&nbsp;&nbsp; $\text{for }\(i=1 \text{ to }\lceil \frac{n}{\text{batchsize}} \rceil\):$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\text{mapcurr} := \text{map.copy}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\text{mapcurr}\[i*\text{batchsize}, \text{ min}\(n, \\; \(i+1\)\*\text{batchsize}\)\] \text{ += indicatorvars}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $A_{i} := \text{mapcurr}(A)$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\sigma := eig(A_{i}) + \text{midpoint}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\text{coeffs.insert}\(\[\text{digits}\(\sigma_{j}\) - \text{midpointvalue for } j \text{ in range}\(n\)\]\)$  
  
&nbsp;&nbsp;&nbsp;&nbsp; $\text{coeffs} := \[vec\(\text{coeffs}\[:,0\]\), \\; \dots, \\; vec\(\text{coeffs}\[:,n-1\]\)\]$
