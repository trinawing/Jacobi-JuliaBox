# Jacobi-JuliaBox
In [6]:

A = [10 -1 0;-1 10 -2;0 -2 10]
        b = [9;7;6]
        tol = 1e-3
        n = length(b)
        D = zeros(n,n)
        for i = 1:n
            D[i,i] = A[i,i]
end
        L = zeros(n,n)
        U = zeros(n,n)
        for i = 2:n
            for j = 1:i-1
                L[i,j] = -A[i,j]
            end
        end
        for i = 1:n-1
            for j = i+1:n
                U[i,j] = -A[i,j]
end end
        invD = inv(D)
        Tj = invD*(L+U)
        cj = invD*b
        x0 = zeros(n,1)
        x1 = ones(n,1)
        err = norm(x0-x1)
        iterations = 0
        while err > tol
            x1 = Tj*x0 + cj
            err = norm(x0-x1)
            iterations = iterations + 1
            x0 = x1
end
        println(iterations)
        println(x1)
​
