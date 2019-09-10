행렬
====
수, 기호, 수식 등을 네모꼴로 배열한 것. 쉽게 생각하면 말 그대로 **Row & Column**. 정확한 영어 표현은 **Matrix**이다.

표현
----
$$\begin{bmatrix}
a & b & c \\
d & e & f
\end{bmatrix}$$
행렬은 크기에 따라 **(행의 수) × (열의 수) 행렬**로 표현하고, 위 행렬은 **2 × 3 행렬**이라고 말할 수 있다.  
행렬 안에 배열된 구성원은 **성분**, **항**, **원소** 등으로 말하며, 위 행렬에서 $e$는 **(2, 2) 성분**이라고 표현한다. 마찬가지로 **(행, 열)** 이다.

(정리 중)

행렬의 곱
---------

### 스칼라 곱셈
Scalar Multiplication. **스칼라곱 (Scalar Product)** 이 아니며, 해당 내용은 아래 `내적 (점곱)`에 있다.  
행렬에 단일 스칼라 값을 곱하는 연산이며, **행렬의 매 성분마다 스칼라 값을 곱하는 것**이라고 생각하면 편하다.  

즉,
$$6 \times \begin{bmatrix}
7 & 8 & 16 \\
9 & 1 & 2
\end{bmatrix} = \begin{bmatrix}
(7 \times 6) & (8 \times 6) & (16 \times 6) \\
(9 \times 6) & (1 \times 6) & (2 \times 6)
\end{bmatrix}$$
이고, 결과적으로 답은
$$\begin{bmatrix}
42 & 48 & 96 \\
54 & 6 & 12
\end{bmatrix}$$
이다. 이건 졸라 쉽다.

### 내적 (점곱)
Dot Product. 혹은 **스칼라곱 (Scalar Product)** 이라고 한다. 행렬과 행렬끼리 곱할 때 사용하는 연산이다.
> NumPy 함수 : `numpy.dot(np_array_a, np_array_b)`

쪼까 복잡하다. 수식으로 된 설명만 보다가 진절머리나던 중 [그림으로 된 설명](https://www.mathsisfun.com/algebra/matrix-multiplying.html) 보니까 확 이해가 되더라.

이 연산을 사용할 때 조건으로, 좌측 행렬의 열의 수와 우측 행렬의 행의 수가 같거나 혹은 그 반대여야 된다는 것이다. 이렇게 같은 수를 $x$라고 치면, 연산의 결과는 **$x \times x$ 행렬**이다.

먼저 예시로,
$$행렬 \textbf{A} = \begin{bmatrix}
5 & 6 & 7 \\
4 & 3 & 2
\end{bmatrix}, 행렬 \textbf{B} = \begin{bmatrix}
8 & 9 \\
1 & 0 \\
10 & 12
\end{bmatrix}$$
이 있다고 한다면,
$$\textbf{A} \cdot \textbf{B} = \begin{bmatrix}
(5 \cdot 8 + 6 \cdot 1 + 7 \cdot 10) & (5 \cdot 9 + 6 \cdot 0 + 7 \cdot 12) \\
(4 \cdot 8 + 3 \cdot 1 + 2 \cdot 10) & (4 \cdot 9 + 3 \cdot 0 + 2 \cdot 12)
\end{bmatrix}$$
이고, 따라서
$$\textbf{A} \cdot \textbf{B} = \begin{bmatrix}
116 & 129 \\
55 & 69
\end{bmatrix}$$
이다. 다르게 표현하면,
$$\textbf{A} \cdot \textbf{B} = \begin{bmatrix}
((\textbf{A}_{(0, 0)} \cdot \textbf{B}_{(0, 0)}) + (\textbf{A}_{(0, 1)} \cdot \textbf{B}_{(1, 0)}) + (\textbf{A}_{(0, 2)} \cdot \textbf{B}_{(2, 0)})) & ((\textbf{A}_{(0, 0)} \cdot \textbf{B}_{(0, 1)}) + (\textbf{A}_{(0, 1)} \cdot \textbf{B}_{(1, 1)}) + (\textbf{A}_{(0, 2)} \cdot \textbf{B}_{(2, 1)})) \\
((\textbf{A}_{(1, 0)} \cdot \textbf{B}_{(0, 0)}) + (\textbf{A}_{(1, 1)} \cdot \textbf{B}_{(1, 0)}) + (\textbf{A}_{(1, 2)} \cdot \textbf{B}_{(2, 0)})) & ((\textbf{A}_{(1, 0)} \cdot \textbf{B}_{(0, 1)}) + (\textbf{A}_{(1, 1)} \cdot \textbf{B}_{(1, 1)}) + (\textbf{A}_{(1, 2)} \cdot \textbf{B}_{(2, 1)}))
\end{bmatrix}$$
인데, 더 복잡하게 느껴지는 건 기분탓이니 넘어가자.

(정리 중)