### second order derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the second order derivative is calculated by deriving the [[derivative]] $Df(x)$ wich is a [[bounded linear map]] is derived again
$$
D^2f(x) = D(Df)(x)
$$
- while the [[derivative]] $Df(x)[h]: X \to Y$ is a [[function]] that mappes $X$ to the space of [[bounded linear map]] from $X$ to $Y$ the second order derivative is mapping $X$ to a [[bounded linear map]] that maps $X$ to a [[bounded linear map]] from $X$ to $Y$ 

$$
D^2f(x)[h][k]: X \to L\left(X, L(X, Y)\right)
$$
- because of the [[linear map|linearity]] we can transform $L(X, L(X, Y))$ to a [[bounded linear map]] from $X \times X$ to $Y$
$$
D^2f(x)[h, k]: X \to L\left(X \times X, Y\right)
$$
### interpretation second order derivative

# ----------------
![[derivative#general derivative]]