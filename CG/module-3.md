# 2D Transformations
_KTU Module 3_

---
### 1.  Translation
Process of changing the position a straight line path from one coordinate to another.

Suppose the original position is <img src="https://i.upmath.me/svg/(x%2Cy)" alt="(x,y)" /> then the new position is
<img src="https://i.upmath.me/svg/(x'%2Cy')" alt="(x',y')" />.
Here  

<img src="https://i.upmath.me/svg/x'%3D%20x%2Bt_x%20%5C%5C%20%0Ay'%3Dy%2Bt_y%20" alt="x'= x+t_x \\ 
y'=y+t_y " />

_**Translation (Matrix Form):**_ 

<img src="https://i.upmath.me/svg/P'%20%3D%20P%2BT" alt="P' = P+T" /> 

<img src="https://i.upmath.me/svg/%0AP%20%3D%20%5Cbegin%7Bbmatrix%7Dx%5C%5C%20y%5Cend%7Bbmatrix%7D%0AP'%20%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%20%0AT'%20%3D%20%5Cbegin%7Bbmatrix%7Dt_x%5C%5C%20t_y%5Cend%7Bbmatrix%7D%0A" alt="
P = \begin{bmatrix}x\\ y\end{bmatrix}
P' = \begin{bmatrix}x'\\ y'\end{bmatrix} 
T' = \begin{bmatrix}t_x\\ t_y\end{bmatrix}
" />

---
### 2.Rotation
Process of repositioning an object along a circular path in the x-y plane.

Using standard Trigonometric equations we can express the transformed coordinates in terms of <img src="https://i.upmath.me/svg/%5Ctheta" alt="\theta" /> and <img src="https://i.upmath.me/svg/%5Cphi" alt="\phi" /> as

<img src="https://i.upmath.me/svg/x'%20%3D%20r%20cos(%5Cphi%20%2B%20%5Ctheta)%20%3D%20r%20cos(%5Cphi)cos(%5Ctheta)-%20r%20sin(%5Cphi)sin(%5Ctheta)%5C%5C%0Ay'%20%3D%20r%20cos(%5Cphi%20%2B%20%5Ctheta)%20%3D%20r%20cos(%5Cphi)sin(%5Ctheta)%2B%20r%20sin(%5Cphi)cos(%5Ctheta)%20" alt="x' = r cos(\phi + \theta) = r cos(\phi)cos(\theta)- r sin(\phi)sin(\theta)\\
y' = r cos(\phi + \theta) = r cos(\phi)sin(\theta)+ r sin(\phi)cos(\theta) " />

_Note: <img src="https://i.upmath.me/svg/%5Ctheta" alt="\theta" /> is considered NEGATIVE when rotating clockwise._

_**Rotation (Matrix Form):**_ 

<img src="https://i.upmath.me/svg/%20P'%20%3D%20P%20.%20R%20" alt=" P' = P . R " />

<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%20%3D%20%0A%5Cbegin%7Bbmatrix%7Dcos%20%5Ctheta%5C%20-sin%5Ctheta%20%5C%5C%20sin%5Ctheta%20%5C%20%5C%20cos%5Ctheta%20%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%5C%5C%20y%5Cend%7Bbmatrix%7D%20%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix} = 
\begin{bmatrix}cos \theta\ -sin\theta \\ sin\theta \ \ cos\theta \end{bmatrix}
. \begin{bmatrix}x\\ y\end{bmatrix} 
" /> 

Homogeneous Form:


<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%20%5C%5C%201%20%5Cend%7Bbmatrix%7D%20%3D%20%0A%5Cbegin%7Bbmatrix%7Dcos%20%5Ctheta%5C%20-sin%5Ctheta%20%5C%200%20%5C%5C%20sin%5Ctheta%20%5C%20%5C%20%5C%20%5C%20cos%5Ctheta%20%0A%5C%200%20%5C%5C%200%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%200%20%20%5C%20%5C%20%5C%20%5C%201%20%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%20%0A" alt="
P'= \begin{bmatrix}x'\\ y' \\ 1 \end{bmatrix} = 
\begin{bmatrix}cos \theta\ -sin\theta \ 0 \\ sin\theta \ \ \ \ cos\theta 
\ 0 \\ 0 \ \ \ \ \ \ \ \ \ 0  \ \ \ \ 1 \end{bmatrix}
. \begin{bmatrix}x\\ y \\ 1\end{bmatrix} 
" /> 

---

### 3.Scaling

Process of changing the size of an object.

It can be performed by multiplying the coordinates of a polygon with Scaling Factors <img src="https://i.upmath.me/svg/S_x" alt="S_x" /> and <img src="https://i.upmath.me/svg/S_y" alt="S_y" />.

_**Scaling (Matrix Form):**_ 

<img src="https://i.upmath.me/svg/%20P'%20%3D%20P%20.%20S%20" alt=" P' = P . S " />

<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%20%0A%3D%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%5Cend%7Bbmatrix%7D%20%0A.%20%5Cbegin%7Bbmatrix%7D%20S_x%5C%200%20%5C%5C%200%5C%20S_y%5Cend%7Bbmatrix%7D%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix} 
= \begin{bmatrix}x \\ y\end{bmatrix} 
. \begin{bmatrix} S_x\ 0 \\ 0\ S_y\end{bmatrix}
" /> 

Homogeneous Form:

<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%20S_x%20%5C%200%20%5C%200%5C%5C%200%20%5C%20S_y%5C%200%20%5C%5C%200%5C%20%5C%200%5C%20%5C%201%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix}
= \begin{bmatrix} S_x \ 0 \ 0\\ 0 \ S_y\ 0 \\ 0\ \ 0\ \ 1\end{bmatrix}
. \begin{bmatrix}x \\ y \\ 1\end{bmatrix}
" /> 


---

### 4.Reflection

Process of producing a mirror image of an object across an axis.

It can also obtained by rotating the object <img src="https://i.upmath.me/svg/180%5Eo" alt="180^o" /> about the reflection axis.


_**Reflection (Matrix Form):**_ 

<img src="https://i.upmath.me/svg/%20P'%20%3D%20P%20.%20R_%7Bef%7D%20" alt=" P' = P . R_{ef} " />

(Reflextion about X-Axis) <img src="https://i.upmath.me/svg/R_x%3D-1" alt="R_x=-1" /> else <img src="https://i.upmath.me/svg/R_x%3D1" alt="R_x=1" />

(Reflextion about Y-Axis) <img src="https://i.upmath.me/svg/R_y%3D-1" alt="R_y=-1" /> else <img src="https://i.upmath.me/svg/R_y%3D1" alt="R_y=1" />


<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%20R_y%20%5C%200%20%5C%5C%200%20%5C%20R_x%20%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%5Cend%7Bbmatrix%7D%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix}
= \begin{bmatrix} R_y \ 0 \\ 0 \ R_x \end{bmatrix}
. \begin{bmatrix}x \\ y\end{bmatrix}
" /> 

_Homogeneous Form:_

<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%20R_y%20%5C%200%20%5C%200%5C%5C%200%20%5C%20R_x%20%5C%200%20%5C%5C%200%20%5C%20%5C%200%20%5C%20%5C%201%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix}
= \begin{bmatrix} R_y \ 0 \ 0\\ 0 \ R_x \ 0 \\ 0 \ \ 0 \ \ 1\end{bmatrix}
. \begin{bmatrix}x \\ y \\ 1\end{bmatrix}
" /> 


---

### 4.Shearing

Process that distorts the shape of an object.

There are two types of shearing:
 - X-Shearing
 - Y-Shearing



_**Shearing (Homogeneous Matrix Form):**_ 

_X - Shearing_

<img src="https://i.upmath.me/svg/%0A%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%201%20%5C%20%5C%200%20%20%5C%20%5C%200%20%5C%5C%20Sh_x%201%20%5C%200%20%5C%5C%20%201%5C%20%5C%201%5C%20%5C%201%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A" alt="
\begin{bmatrix}x'\\ y' \\ 1\end{bmatrix}
= \begin{bmatrix} 1 \ \ 0  \ \ 0 \\ Sh_x 1 \ 0 \\  1\ \ 1\ \ 1\end{bmatrix}
. \begin{bmatrix}x \\ y \\ 1\end{bmatrix}
" /> 

_Y - Shearing_

<img src="https://i.upmath.me/svg/%0A%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7D%201%5C%20Sh_y%20%5C%200%20%5C%5C0%20%5C%20%5C%201%20%5C%20%5C%200%20%5C%5C%20%201%5C%20%5C%201%5C%20%5C%201%5Cend%7Bbmatrix%7D%0A" alt="
\begin{bmatrix}x'\\ y' \\ 1\end{bmatrix}
= \begin{bmatrix}x \\ y \\ 1\end{bmatrix}
. \begin{bmatrix} 1\ Sh_y \ 0 \\0 \ \ 1 \ \ 0 \\  1\ \ 1\ \ 1\end{bmatrix}
" /> 
