$\text{eig(A, batchsize, stagger): }$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{n, extractionparams (ep), midpoint, midpointvalue, digits, symbols} := \dots$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{digits} := \text{batchsize}\*\(\text{stagger}+1\)$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{ep.indicatorvars} := \[\text{base}^{\lceil \frac{\text{digits}}{2} \rceil - \text{stagger}} \\; \text{base}^{\lceil \frac{\text{digits}}{2} \rceil - 2*\text{stagger}} \\; \dots \\; \text{base}^{-\lfloor \frac{\text{digits}}{2} \rfloor}\]$    
&nbsp;&nbsp;&nbsp;&nbsp;$\text{ep.realvals} \gets \[ \dots \]$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{map} \gets \\{\text{symbols} \rightarrow \text{randomreals}\\}$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{coeffs} := \[\]$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{for }\(i=1 \text{ to }\lceil \frac{\text{n}}{\text{batchsize}} \rceil\):$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\text{mapcurr} := \text{map.copy()}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\text{mapcurr}\[i*\text{batchsize}, \min{\(\text{n}, \(i+1\)\*\text{batchsize}\)}\] \text{ += expvars}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $A_{i} := \text{mapcurr(A)}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\sigma := eig(A_{i}) + \text{midpoint}$  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $\text{coeffs.insert}\(\[\text{digits}\(\sigma_{j}\) - \text{midpointvalue for j in range\(n\)}\]\)$  
&nbsp;&nbsp;&nbsp;&nbsp;$\text{coeffs} := \[vec\(\text{coeffs}\[:,0\]\) \\; \dots \\; vec\(\text{coeffs}\[:,n-1\]\)\]$

