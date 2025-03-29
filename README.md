# Calculadora de IMC

## 🏋️‍♀️ Sobre o Projeto
Este projeto é uma calculadora de IMC (Índice de Massa Corporal) desenvolvida para dispositivos Android, utilizando Java e Android Studio. A aplicação permite que os usuários calculem o seu IMC inserindo sua altura e peso, oferecendo uma classificação do resultado conforme as diretrizes da Organização Mundial da Saúde (OMS).

## 💻 Tecnologias Utilizadas

| Tecnologia | Descrição |
|------------|-----------|
| [Android Studio](https://developer.android.com/studio) | IDE para desenvolvimento de aplicativos Android |
| Java | Linguagem de programação utilizada |
| XML | Linguagem para criação da interface de usuário |
| Gradle | Sistema de automação de build utilizado no projeto |

## 🎮 Como Usar
1. Abra o aplicativo em um dispositivo Android ou em um emulador.
2. Insira seu peso (em kg) e sua altura (em metros).
3. Toque no botão "Calcular" para obter seu IMC.
4. O aplicativo exibirá o IMC calculado e sua classificação conforme a tabela da OMS:
   - Abaixo do peso: IMC < 18,5
   - Peso normal: 18,5 ≤ IMC < 24,9
   - Sobrepeso: 25 ≤ IMC < 29,9
   - Obesidade: IMC ≥ 30

## 🛠️ Estrutura do Código

Abaixo está um exemplo de como o código realiza o cálculo do IMC:

```java
public class MainActivity extends AppCompatActivity {
    EditText etPeso, etAltura;
    TextView tvResultado;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        etPeso = findViewById(R.id.etPeso);
        etAltura = findViewById(R.id.etAltura);
        tvResultado = findViewById(R.id.tvResultado);

        Button btnCalcular = findViewById(R.id.btnCalcular);
        btnCalcular.setOnClickListener(v -> calcularIMC());
    }

    private void calcularIMC() {
        double peso = Double.parseDouble(etPeso.getText().toString());
        double altura = Double.parseDouble(etAltura.getText().toString());

        double imc = peso / (altura * altura);

        String classificacao = "";
        if (imc < 18.5) {
            classificacao = "Abaixo do peso";
        } else if (imc >= 18.5 && imc < 24.9) {
            classificacao = "Peso normal";
        } else if (imc >= 25 && imc < 29.9) {
            classificacao = "Sobrepeso";
        } else {
            classificacao = "Obesidade";
        }

        tvResultado.setText("IMC: " + String.format("%.2f", imc) + "\n" + classificacao);
    }
}
```

## 🛠️ Configuração do Projeto
1. Abra o Android Studio.
2. Clone este repositório ou baixe os arquivos do projeto.
3. Abra o projeto no Android Studio.
4. Execute o aplicativo em um emulador ou dispositivo Android conectado.

## 🤝 Desenvolvimento do Projeto
- Daniel Kyoshi Moribe
- RA: 24026509
- Estudante de Ciências da Computação
- Desenvolvido com o objetivo de obter nota através da avaliação N1 da matéria Programação Para Dispositivos Móveis
- Professor orientador: Vinicius Heltai Pacheco

## 🚀 Processo de Desenvolvimento
### Desafios Encontrados
1. Solução de problemas
2. Tratamento de inputs inválidos
3. Transferência de informações entre telas

## Licença
Este projeto é distribuído sob a [licença MIT](https://mit-license.org/). Para mais informações, consulte o arquivo LICENSE.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
