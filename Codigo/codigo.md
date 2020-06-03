### Desarrollo



##### Tecnologías a utilizar

- Lenguaje Python
- libreria **NLTK**
- Google colab



Importamos la libreria **nltk** y descargamos uno de sus corpus 

```python
import nltk

nltk.dowload('cess_esp')
```



##### Expresiones Regulares

Importamos la libreria para expresiones regulares (**re**)

```python
corpus = nltk.corpus.cess_esp.sents()
print(corpus) #este corpus ya esta tokenizado
print(len(corpus)) #titulares de noticias en español

```



Como nuestros corpus se encuentran en una lista, la recorremos, para ello asignamos la variable **flatten**

```python
flatten = [w for i in corpus for w in i]
print(f'cantidad de tokens {len(flatten)}')
print(flatten[:20])
```



Llamamos el método **search()** de la libreria **re**

```python
arr = [w for w in flatten if re.search('es',w)]
print(arr[:10])

arr = [w for w in flatten if re.search('es$',w)]

print(arr[:10])

arr = [w for w in flatten if re.search('^es',w)]

print(arr[:10])

# Rango [a-z] [ghi]
arr = [w for w in flatten if re.search('^[ghi]',w)]

print(arr[:10])

# Clasura
# * repetir 0 o mas veces
# + repetir 1 o mas veces

arr = [w for w in flatten if re.search('^(no)+',w)]
print(arr[:20])
```



Como resultado podemos observar dentro de nuestro método **re.search**() los parámetros que le pasamos, es indispensable tener conocimientos sobre **expresiones regulares**