# SmartHome 🏠💡📺🔊

Projeto em C++ que simula uma **Casa Inteligente** utilizando conceitos de **Programação Orientada a Objetos (POO)**.  
O sistema integra dispositivos como luzes, caixas de som, Smart TVs e câmeras de segurança, demonstrando **composição, agregação, herança múltipla, polimorfismo e associação**.

---

## 📂 Estrutura do Projeto

- **SmartHome.h** → Declaração das classes e interfaces
- **SmartHome.cpp** → Implementação dos métodos
- **main.cpp** → Execução e demonstração dos conceitos

---

## 🚀 Funcionalidades

- **Composição**:  
  A classe `CasaInteligente` possui um `HubIA`, criado e destruído junto com a casa.

- **Agregação**:  
  A classe `Comodo` agrega dispositivos (`DispositivoSmart*`), mas não gerencia seu ciclo de vida.

- **Herança múltipla**:  
  A classe `SmartTV` herda de `DispositivoSmart` e `InterfaceTela`.

- **Herança protegida**:  
  A classe `CameraSeguranca` herda de `ComponenteRede` de forma protegida, ocultando atributos como IP e nível de sinal.

- **Polimorfismo**:  
  O método `ligar()` é sobrescrito em cada dispositivo (`LuzInteligente`, `CaixaDeSom`, `SmartTV`), permitindo comportamentos distintos.

- **Associação simples**:  
  A classe `Morador` pode usar dispositivos sem ser dona deles.

---

## 🛠️ Exemplos de Uso

No `main.cpp` você encontra exemplos práticos:

```cpp
// Criando a casa inteligente
CasaInteligente minhaCasa;
minhaCasa.gerenciarCasa();

// Instanciando dispositivos
CaixaDeSom som("192.168.1.10", 90, "Som Ambiente");
LuzInteligente luz("192.168.1.11", 85, "Luz Principal");
SmartTV tv("192.168.1.12", 95, "Smart TV Sala");

// Herança protegida
CameraSeguranca cam("192.168.1.50", 100, "Portão Principal");
cam.monitorar();

// Agregação e polimorfismo
Comodo sala("Sala de Estar");
sala.adicionarDispositivo(&som);
sala.adicionarDispositivo(&luz);
sala.adicionarDispositivo(&tv);
sala.ativarCena();

// Associação simples
Morador habitante("Rafael");
habitante.usarDispositivo(&tv);
```

---

## ⚙️ Como Compilar e Executar

No terminal:

```bash
g++ main.cpp SmartHome.cpp -o smarthome
./smarthome
```

---

## 🎯 Objetivo Didático

Este projeto foi desenvolvido para **demonstrar conceitos fundamentais de POO em C++** aplicados a um cenário realista de **automação residencial**.  
Ele pode ser usado como **material de estudo** para entender:
- Diferença entre composição e agregação
- Herança múltipla e protegida
- Polimorfismo em métodos virtuais
- Associação entre classes
  
