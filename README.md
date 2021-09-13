# Matrix
### 旋转矩阵
### 4元数与旋转轴
    绕旋转轴[nx,ny,nz]转θ角的四元素为
    q=[cos(θ/2),nx*sin(θ/2),ny*sin(θ/2)，nz*sin(θ/2)]
    对应的旋转矩阵为R
    https://en.wikipedia.org/wiki/Rotation_matrix
    R= 
        cosθ+ux^2(1-cosθ)  uxuy(1-cos)-uzsin  uxuz(1-cos)+uysin
        uyux(1-cos)+uzsin  cos+uy^2(1-cos)    uyuz(1-cos)-uxsin
        uzux(11-cos)-uysin  uzuy(1-cos)+uxsin  cos+uz(1-cos)
    

    对应的Eigen代码
    AngleAxis<float> aa;
    aa.angle() = angle * PI / 180.0f;
    aa.axis() = { n[0], n[1], n[2] };
    Matrix3f m = aa.toRotationMatrix();
    
    或者从4元素一般形式推导旋转矩阵
    https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation
    q=q0+q1i+q2j+q3k
    R=
    1-2q2^2-2q3^2 ...
    
    
