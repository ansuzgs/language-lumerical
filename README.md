# language-lumerical

Syntax highlighting for Lumerical in Atom.

[<img src="https://github.com/favicon.ico" height="20"> GitHub](http://github.com/ansuzgs/language-lumerical)  
[<img src="https://atom.io/favicon.ico" height="20"> Atom](https://atom.io/packages/language-lumerical)


# Shortcuts

Some shortcuts:

* `for` + <kbd>Tab</kbd>

```lumerical
for(var = start:end) {
  #body
}
```

* `if` + <kbd>Tab</kbd>

```lumerical
if(var operator var) {
  #body
}
```

* `ife` + <kbd>Tab</kbd>

```lumerical
if(var operator var) {
  #body
} else {
  #body
}
```

* `sw` + <kbd>Tab</kbd>

```lumerical
switchtolayout;
```

* `r` + <kbd>Tab</kbd>

```lumerical
run;
```

* `gr` + <kbd>Tab</kbd>

```lumerical
getresult(monitor, var);
```

* `wr` + <kbd>Tab</kbd>

```lumerical
write(filename, var);
```

* `s1` + <kbd>Tab</kbd>

```lumerical
# Crear el vector del sweep
param = [start:step:end]*1e-9;

# Seleccionar elemento a modificar
select("elem");

# Iniciamos bucle de la simulacion
for(i = 1:length(param)){
   ?"Simulation: "i;

   switchtolayout; # Volvemos al modo layout

   # Modificando la propiedad del elemento
   set("property",param(i));

   # Computamos la simulacion
   run;

   # Obtenemos los resultados
   T = getresult("monitor", "variable");

   # Almacenamos los resultados en un txt (csv)
   for(j = 1:length(T.T)) {
       write("path/"+num2str(i)+"_"+param+"_"+num2str(param(i))+".txt", num2str(T.lambda(j))+", "+num2str(T.T(j)));
   }
 }
 ```
