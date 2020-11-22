# 2D Transformations
_KTU Module 3_


---
Syllabus
---

- Two Dimensional Transformations.
  - Homogeneous coordinate systems
  - Matrix Formulation and Concatenation of Transformations.
- Windowing concepts 
  - Window to Viewport Transformation
  - Two Dimensional Line clipping
    - Cohen Sutherland Line
    - Midpoint Subdivision Algorithm

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

##### Homogeneous Form:

<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%20%5C%5C%201%20%5Cend%7Bbmatrix%7D%20%3D%20%0A%5Cbegin%7Bbmatrix%7D1%20%5C%200%20%5C%20t_x%20%5C%5C%200%20%5C%201%20%5C%20t_y%20%5C%5C%200%20%20%5C%200%20%20%5C%20%201%20%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%20%0A" alt="
P'= \begin{bmatrix}x'\\ y' \\ 1 \end{bmatrix} = 
\begin{bmatrix}1 \ 0 \ t_x \\ 0 \ 1 \ t_y \\ 0  \ 0  \  1 \end{bmatrix}
. \begin{bmatrix}x\\ y \\ 1\end{bmatrix} 
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

##### Homogeneous Form:

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

<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%20%0A%3D%20%5Cbegin%7Bbmatrix%7D%20S_x%5C%200%20%5C%5C%200%5C%20S_y%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%5Cend%7Bbmatrix%7D%20%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix} 
= \begin{bmatrix} S_x\ 0 \\ 0\ S_y\end{bmatrix}
. \begin{bmatrix}x \\ y\end{bmatrix} 
" /> 

##### Homogeneous Form:

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

(Reflection about X-Axis) <img src="https://i.upmath.me/svg/R_x%3D-1" alt="R_x=-1" /> else <img src="https://i.upmath.me/svg/R_x%3D1" alt="R_x=1" />

(Reflection about Y-Axis) <img src="https://i.upmath.me/svg/R_y%3D-1" alt="R_y=-1" /> else <img src="https://i.upmath.me/svg/R_y%3D1" alt="R_y=1" />


<img src="https://i.upmath.me/svg/%0AP'%3D%20%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%20R_y%20%5C%200%20%5C%5C%200%20%5C%20R_x%20%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%5Cend%7Bbmatrix%7D%0A" alt="
P'= \begin{bmatrix}x'\\ y'\end{bmatrix}
= \begin{bmatrix} R_y \ 0 \\ 0 \ R_x \end{bmatrix}
. \begin{bmatrix}x \\ y\end{bmatrix}
" /> 

##### Homogeneous Form:

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



##### Shearing (Homogeneous Matrix Form):

_X - Shearing_

<img src="https://i.upmath.me/svg/%0A%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%201%20%5C%20%5C%200%20%20%5C%20%5C%200%20%5C%5C%20Sh_x%201%20%5C%200%20%5C%5C%20%201%5C%20%5C%201%5C%20%5C%201%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A" alt="
\begin{bmatrix}x'\\ y' \\ 1\end{bmatrix}
= \begin{bmatrix} 1 \ \ 0  \ \ 0 \\ Sh_x 1 \ 0 \\  1\ \ 1\ \ 1\end{bmatrix}
. \begin{bmatrix}x \\ y \\ 1\end{bmatrix}
" /> 

_Y - Shearing_

<img src="https://i.upmath.me/svg/%0A%5Cbegin%7Bbmatrix%7Dx'%5C%5C%20y'%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A%3D%20%5Cbegin%7Bbmatrix%7D%201%5C%20Sh_y%20%5C%200%20%5C%5C0%20%5C%20%5C%201%20%5C%20%5C%200%20%5C%5C%20%201%5C%20%5C%201%5C%20%5C%201%5Cend%7Bbmatrix%7D%0A.%20%5Cbegin%7Bbmatrix%7Dx%20%5C%5C%20y%20%5C%5C%201%5Cend%7Bbmatrix%7D%0A" alt="
\begin{bmatrix}x'\\ y' \\ 1\end{bmatrix}
= \begin{bmatrix} 1\ Sh_y \ 0 \\0 \ \ 1 \ \ 0 \\  1\ \ 1\ \ 1\end{bmatrix}
. \begin{bmatrix}x \\ y \\ 1\end{bmatrix}
" /> 

---

## Window View-port Transformation

<img src="https://i.upmath.me/svg/%5Cbegin%7Btikzpicture%7D%5Bx%3D1cm%2C%20y%3D1cm%2C%20z%3D-0.6cm%5D%0A%20%20%20%20%25%20Axes%0A%20%20%20%20%5Cdraw%20%5B-%2Cdashed%5D%20(0%2C-1)%20--%20(0%2C5)%3B%0A%20%20%20%20%5Cdraw%20%5B-%2Cdashed%5D%20(4%2C-1)%20--%20(4%2C5)%3B%0A%20%20%20%20%5Cdraw%20%5B-%2Cdashed%5D%20(-1%2C0)%20--%20(5%2C0)%3B%0A%20%20%20%20%5Cdraw%20%5B-%2Cdashed%5D%20(-1%2C4)%20--%20(5%2C4)%3B%0A%20%20%20%20%5Cdraw%20(0%2C0)%20--%20(4%2C0)%20--%20(4%2C4)%20--%20(0%2C4)%20--%20(0%2C0)%3B%0A%5Cnode%20%5Bleft%5D%20at%20(4%2C-1)%20%7B%24X_%7Bmax%7D%24%7D%3B%0A%5Cnode%20%5Bleft%5D%20at%20(0%2C-1)%20%7B%24X_%7Bmin%7D%24%7D%3B%0A%5Cnode%20%5Bleft%5D%20at%20(-1%2C4)%20%7B%24Y_%7Bmax%7D%24%7D%3B%0A%5Cnode%20%5Bleft%5D%20at%20(-1%2C0)%20%7B%24Y_%7Bmin%7D%24%7D%3B%0A%5Cend%7Btikzpicture%7D" alt="\begin{tikzpicture}[x=1cm, y=1cm, z=-0.6cm]
    % Axes
    \draw [-,dashed] (0,-1) -- (0,5);
    \draw [-,dashed] (4,-1) -- (4,5);
    \draw [-,dashed] (-1,0) -- (5,0);
    \draw [-,dashed] (-1,4) -- (5,4);
    \draw (0,0) -- (4,0) -- (4,4) -- (0,4) -- (0,0);
\node [left] at (4,-1) {$X_{max}$};
\node [left] at (0,-1) {$X_{min}$};
\node [left] at (-1,4) {$Y_{max}$};
\node [left] at (-1,0) {$Y_{min}$};
\end{tikzpicture}" />

### Cohen Sutherland Line Clipping.

#### Concept

1. Assign the region code for 2 end points of a given line
2. If both have region codes `0000` then lines accepted completely.
3. Else
   - Perform logical AND operation for both region codes
   - If `result !=0`, `lin` is outside
   - Else line is partially inside.
       - Choose an end point of the line that is outside the given rectangle.
       - Find the intersection point
       - Replace <img src="https://i.upmath.me/svg/i%5E%7Bth%7D" alt="i^{th}" /> endpoint with the intersection point and update the region code.
       - Repeat `step 2` until line is trivially accepted or trivially rejected.
4. Repeat step 1 for other lines.

#### Algorithm
1. Assign the region code for 2 end points of a given line <img src="https://i.upmath.me/svg/C_0" alt="C_0" /> and <img src="https://i.upmath.me/svg/C_1" alt="C_1" />
2. If <img src="https://i.upmath.me/svg/C_0" alt="C_0" /> OR <img src="https://i.upmath.me/svg/C_1" alt="C_1" />==`0000` then accept completely.
3. Else if <img src="https://i.upmath.me/svg/C_0" alt="C_0" /> AND <img src="https://i.upmath.me/svg/C_0" alt="C_0" /> !=`0000` Reject it
4. Else  
   - If line crossed <img src="https://i.upmath.me/svg/X_%7Bmin%7D" alt="X_{min}" /> or <img src="https://i.upmath.me/svg/X_%7Bmax%7D" alt="X_{max}" /> , Clip
      - <img src="https://i.upmath.me/svg/y%20%3D%20y_1%20%2B%20m(x%20-%20x_1)" alt="y = y_1 + m(x - x_1)" />
   - If line crossed <img src="https://i.upmath.me/svg/Y_%7Bmin%7D" alt="Y_{min}" /> or <img src="https://i.upmath.me/svg/Y_%7Bmax%7D" alt="Y_{max}" /> , Clip
      - <img src="https://i.upmath.me/svg/x%20%3D%20x_1%20%2B%20%5Cfrac%7B1%7D%7Bm%7D%20(y%20-%20y_1)" alt="x = x_1 + \frac{1}{m} (y - y_1)" />
   - Verify 
      - <img src="https://i.upmath.me/svg/x_%7Bmin%7D%20%5Cleq%20x%20%5Cleq%20x_%7Bmax%7D%20" alt="x_{min} \leq x \leq x_{max} " />
      - <img src="https://i.upmath.me/svg/y_%7Bmin%7D%20%5Cleq%20y%20%5Cleq%20y_%7Bmax%7D%20" alt="y_{min} \leq y \leq y_{max} " />
   - If it does not satisy, then repeat the clipping process.

---

### Midpoint Division Algorithm

1. Calculate the position of both endpoints of the line
2. Perform OR operation on both of these endpoints
3. If the OR operation gives 0000
   then
   - Line is guaranteed to be visible
   - else
      - Perform AND operation on both endpoints.
      - If AND <img src="https://i.upmath.me/svg/%5Cne" alt="\ne" /> `0000`
          - then the line is Invisible
      - else (AND=0000)
          - then the line is Clipped.
4. For the line to be clipped. Find midpoint
    - <img src="https://i.upmath.me/svg/X_m" alt="X_m" /> is midpoint of X coordinate.
    - <img src="https://i.upmath.me/svg/Y_m" alt="Y_m" /> is midpoint of Y coordinate.

<img src="https://i.upmath.me/svg/Xm%3D%20%5Cfrac%7B(x1%2Bx2)%7D%7B2%7D%20" alt="Xm= \frac{(x1+x2)}{2} " />

<img src="https://i.upmath.me/svg/Ym%3D%5Cfrac%7B(y1%2By2)%7D%7B2%7D" alt="Ym=\frac{(y1+y2)}{2}" />

5. Check each midpoint, whether it nearest to the boundary of a window or not.
6. If the line is totally visible or totally rejected not found then Repeat `step 1 to 5`.
7. Stop algorithm.

---
