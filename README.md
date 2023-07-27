# studyME

> Modificadores de acesso 

## Public
 > O modificador de acesso public é o mais permissivo de todos. Uma classe, atributo ou método declarado como public pode ser acessado por qualquer classe em qualquer pacote. Ou seja, ele possui visibilidade pública e pode ser utilizado livremente. Por exemplo:
```
public class Conta {

  public double saldo;

  public void sacar(double valor) {
    // lógica de saque...
  }
}

public class Principal {

    public static void main(String[] args) {
        Conta c1 = new Conta();
        c1.saldo = 300;
        c1.sacar(100);
    }

}
```

## Default (Package-private)
> O modificador de acesso default é aquele que não especifica nenhum modificador de acesso. Quando nenhum modificador de acesso é especificado, a classe, atributo ou método pode ser acessado apenas pelas classes que estão no mesmo pacote. Por exemplo:
```
package br.com.alura.conta;

public class Conta {

  double saldo;

  void sacar(double valor) {
    // lógica de saque...
  }
}

package br.com.alura.testes;

public class Principal {

    public static void main(String[] args) {
        Conta c1 = new Conta();
        c1.saldo = 300;
        c1.sacar(100);
    }

}
```
No código anterior, a classe <strong>Conta</strong> está em um pacote e a classe <strong>Principal</strong> em outro pacote distinto. A classe <strong>Conta</strong> pode ser instanciada dentro da classe <strong>Principal</strong>, pois ela possui o modificador de acesso <strong>public</strong>, entretanto, o atributo saldo e o método sacar tem o modificador <strong>default</strong> e, portanto, não podem ser acessados de dentro da classe Principal, o que vai causar um erro de compilação no código anterior.

## Private
> O modificador de acesso private é o mais restritivo de todos. Uma classe, atributo ou método declarado como private só pode ser acessado dentro da própria classe. Ou seja, ele possui visibilidade restrita e não pode ser utilizado por outras classes. Por exemplo:

```
public class Conta {

  private double saldo;

  private void sacar(double valor) {
    // lógica de saque...
  }
} 

public class Principal {

    public static void main(String[] args) {
        Conta c1 = new Conta();
        c1.saldo = 300;
        c1.sacar(100);
    }
}

```

No código anterior, vai ocorrer erro de compilação na classe <strong>Principal</strong>, pois o atributo saldo e o método sacar foram declarados como <strong>private</strong>, não podendo com isso serem acessados de fora da própria classe Conta.


