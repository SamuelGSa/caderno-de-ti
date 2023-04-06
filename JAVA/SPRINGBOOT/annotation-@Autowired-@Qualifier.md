# @Autowired @Qualifier


``@Autowired`` permite que o spring resolva e injete beans de colaboração em nosso bean.

Ao declarar todas as dependências de bean em um arquivo de configuração do Spring, o contêiner Spring pode cnectar automaticamente os relacionamentos entre os brans de colaboração.  Isso é chamado de **autowiring de bean Spring**.

Por padrão, o Spring resolve as entradas @Autowired por tipo. **Se mais de um bean do mesmo tipo estiver disponível no contêiner, o framework lançará uma exceção fatal**.

Podemos usar a anotação ``@Qualifier`` para indicar o bean Necessário

```
@Componet("fooFomatter")
public class FooFomartter implements Formatter {
     public String format() {
          return "foo";
     }
}
```
```

@Componet("barFomatter")
public class BarFormatter implements Formatter {
     public String format() {
          return "bar";
     }
}
```

Como existem duas implementações concretas do Formatter disponívis para o contêiner Spring, o Spring lancará uma exceção (*NoUniqueBeanDefinitionException*)

```
public class FooService {
    @Autowired
    private Formatter formatter;
}
```

Podemos evitar isso usando uma anotação **@Qualifier para evitar ambiguidade**.
```
public class FooService {
    @Autowired
    @Qualifier("fooFormatter")
    private Formatter formatter;
}
```