**NumPy**


---

O NumPy é uma biblioteca que suporta arrays e matrizes multidimensionais. Com suas funções é possível facilitar a execução de operações matemáticas e também de outras tarefas, como Machine Learning e Processamento de Imagem e Computação Gráfica. 
Entre suas funções incorporadas, destacam-se as usadas para álgebra linear
e geração de números aleatórios.


**Importando NumPy**

Caso a biblioteca não esteja instalada, o modo mais fácil é usar o pip para fazer a instalação de sua versão mais recente.


```python
pip install numpy
```

    Requirement already satisfied: numpy in /usr/local/lib/python3.6/dist-packages (1.18.5)
    

Em seguida, basta importar a biblioteca.


```python
import numpy
```

Também podemos importar a biblioteca e usá-la com outro nome.


```python
import numpy as np
```


---
\
**Arrays/Matrizes**




---
\
**O que são arrays em NumPy**

Arrays são estruturas de dados semelhantes às listas, mas com menor flexibiliade. Em um array todos os elementos devem ser de um mesmo tipo, geralmente numérico, como int ou float, e seu tamanho não pode ser modificado.

**Função array**


```python
# Criando um array 

a= np.array([1,2,3])
print(a)
```

    [1 2 3]
    

Com o NumPy, um array pode ser utilizado para criar matrizes. No array abaixo, cada lista de inteiros corresponde a uma linha da matriz. Essas listas devem ter a mesma quantidade de elementos para formar as colunas da matriz.


```python
# Criando uma matriz

A= np.array([[1,2,3],[1,2,3]])
print(A)

# 2 listas de inteiros
# 3 elementos por lista
# Logo, trata-se de uma matriz 2x3
```

    [[1 2 3]
     [1 2 3]]
    

Podemos usar a função shape para verificar as dimensões de um array.


```python
print(A.shape)

# (linhas,colunas)
```

    (2, 3)
    

Dessa forma, é possível criar matrizes com as dimensões que quisermos.


```python
# Matriz 1x3

B= np.array([[1.1,2.2,3.3]])
print(B)

# Também podemos usar números flutuantes (float)
```

    [[1.1 2.2 3.3]]
    


```python
# Matriz 3x4 

C= np.array([[1,0,3,4],[1,0,2,2],[2,3,4,5]])
print(C)
```

    [[1 0 3 4]
     [1 0 2 2]
     [2 3 4 5]]
    


```python
# Matriz 5x3

D= np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12],[13,14,15]])
print(D)
```

    [[ 1  2  3]
     [ 4  5  6]
     [ 7  8  9]
     [10 11 12]
     [13 14 15]]
    


```python
# Matriz 2x1

E= np.array([[1],[2]])
print(E)
```

    [[1]
     [2]]
    

**Operações com matrizes**

Após criar as matrizes, podemos realizar operações com elas.


```python
# Soma 

M= np.array([[1,2],[1,2]])
N= np.array([[2,0],[1,1]])

print(M+N)
```

    [[3 2]
     [2 3]]
    


```python
# Multiplicação por Escalar

print(M*2)
```

    [[2 4]
     [2 4]]
    


```python
# Multiplicação de Matrizes

MN= np.dot(M,N)

print(MN)
```

    [[4 2]
     [4 2]]
    


```python
# Matriz Transposta

M_trp= M.T

print(M_trp)
```

    [[1 1]
     [2 2]]
    

Utilizando o módulo linalg conseguimos realizar ainda mais operações.


```python
# Determinante

N_det= np.linalg.det(N)

print(N_det)
```

    2.0
    


```python
# Matriz Inversa

N_inv= np.linalg.inv(N)

print(N_inv)
```

    [[ 0.5  0. ]
     [-0.5  1. ]]
    

---
\
**Outras Funções**


---
\
**Zeros/Ones**

Cria uma matriz a partir de um único elemento.


```python
# Matriz 3x3 composta por 0

F= np.zeros((3,3))  
print(F)
```

    [[0. 0. 0.]
     [0. 0. 0.]
     [0. 0. 0.]]
    


```python
# Matriz 2x2 composta por 1

G= np.ones((2,2),int)
print(G)
```

    [[1 1]
     [1 1]]
    

**Identity**

Cria uma matriz identidade.


```python
 # No argumento da função escolhemos o tamanho da matriz. 
 # Ex: Matriz 4x4

H= np.identity(4) 
print(H)
```

    [[1. 0. 0. 0.]
     [0. 1. 0. 0.]
     [0. 0. 1. 0.]
     [0. 0. 0. 1.]]
    

**Max**

Informa o maior elemento da matriz.


```python
print(C.max())
```

    5
    

**Min**

Informa o menor elemento da matriz.


```python
print(C.min())
```

    0
    

**Sum**

Retorna a soma de todos os elementos da matriz.


```python
print(A.sum())
```

    12
    

**Mean**

Retorna a média dos elementos da matriz.


```python
print(A.mean())
```

    2.0
    

**Std**

Retorna o desvio padrão. 


```python
print(A.std())
```

    0.816496580927726
    

---
\
**Funções para gerar números aleatórios**

---
\
A biblioteca NumPy inclui o módulo random, que pode ser utilizado para gerar números pseudoaleatórios.

**Função rand**

Retorna um número float entre 0 e 1.


```python
print(np.random.rand())
```

    0.6868741768478481
    

O parâmetro da função determina a quantidade de números aleatórios que devem ser gerados e faz a função retornar um array contendo esses números. 


```python
print(np.random.rand(4))
```

    [0.74910734 0.69779223 0.76155856 0.6559158 ]
    

Dessa forma, é possível criar matrizes usando números flutuantes aleatórios.


```python
# Matriz 3 x 2 com números flutuantes aleatórios entre 0 e 1

I= np.random.rand(3,2)
print(I)
```

    [[0.17488055 0.26818342]
     [0.67671683 0.4621109 ]
     [0.28513144 0.87887645]]
    

**Função randint**

Gera aleatoriamente um número inteiro dentro de um intervalo dado pelo usuário.


```python
# Número inteiro aleatório entre 0 e 50

print(np.random.randint(50)) 
```

    23
    


```python
# Número inteiro aleatório entre 1 e 20

print(np.random.randint(1,20)) 
```

    16
    

O parâmetro size determina a quantidade de números aleatórios que devem ser gerados e faz a função retornar um array contendo esses números.


```python
print(np.random.randint(1,20,size=4))
```

    [4 7 2 1]
    

Dessa forma, é possível criar matrizes usando números inteiros aleatórios.


```python
# Matriz 3 x 3 com números aleatórios entre 1 e 20

J = np.random.randint(1,20, (3,3))
print(J)
```

    [[ 8 19  3]
     [ 3 16 12]
     [18  5  4]]
    


```python
!jupyter nbconvert --to md numpy.ipynb
```

    Traceback (most recent call last):
      File "c:\phyton 38\lib\runpy.py", line 194, in _run_module_as_main
        return _run_code(code, main_globals, None,
      File "c:\phyton 38\lib\runpy.py", line 87, in _run_code
        exec(code, run_globals)
      File "C:\Phyton 38\Scripts\jupyter-nbconvert.EXE\__main__.py", line 7, in <module>
      File "c:\phyton 38\lib\site-packages\jupyter_core\application.py", line 270, in launch_instance
        return super(JupyterApp, cls).launch_instance(argv=argv, **kwargs)
      File "c:\phyton 38\lib\site-packages\traitlets\config\application.py", line 837, in launch_instance
        app.start()
      File "c:\phyton 38\lib\site-packages\nbconvert\nbconvertapp.py", line 350, in start
        self.convert_notebooks()
      File "c:\phyton 38\lib\site-packages\nbconvert\nbconvertapp.py", line 518, in convert_notebooks
        cls = get_exporter(self.export_format)
      File "c:\phyton 38\lib\site-packages\nbconvert\exporters\base.py", line 127, in get_exporter
        raise ExporterNameError('Unknown exporter "%s", did you mean one of: %s?'
    nbconvert.exporters.base.ExporterNameError: Unknown exporter "md", did you mean one of: asciidoc, custom, html, latex, markdown, notebook, pdf, python, rst, script, slides, webpdf?
    


```python

```
