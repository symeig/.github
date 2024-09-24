# Welcome to symeig!   
**`zle-cpp`** A C++ library for evaluating eigenvalues of integer-linear matrices.  
**`zle-py`** A Python library for generating, and evaluating eigenvalues of, integer-linear matrices.  
**`zle-mma`** A Mathematica library for generating, and evaluating eigenvalues of, integer-linear matrices.    

## $\mathbf{Z}\textbf{LE Algorithm Overview}$ 
  
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
  
## $\textbf{Runtime Comparison}$  

![Image Description](runtime_gh.jpg)


Please cite us:  
```bibtex
@misc{xxxx.xxxxx,
  Author = {Jonny Luntzel, Abraham Miller},
  Title = {Fast Symbolic Integer-Linear Spectra},
  Year = {2024},
  Eprint = {arXiv:xxxx.xxxxx},
}
