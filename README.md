[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/UE2m43kj)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=20089752&assignment_repo_type=AssignmentRepo)
# 🚚 Sistema de Simulação Logística

## 📖 Visão Geral

Este é um sistema de simulação para otimização de roteamento logístico. O sistema simula uma rede de distribuição com múltiplos pontos, veículos e pedidos, permitindo testar diferentes estratégias de roteamento.

## 🚀 Execução Rápida

### Pré-requisitos
```bash
# Python 3.8 ou superior
python --version

# Instalar dependências
pip install -r requirements.txt
```

### Executar Simulação
```bash
# Executar simulação básica
python main.py

# Executar testes
python -m pytest tests/

# Executar testes com cobertura
python -m pytest tests/ --cov=.
```

## 🏗️ Estrutura do Sistema

### Componentes Principais

- **`main.py`**: Arquivo principal com exemplo de uso
- **`models/`**: Modelos de dados (Location, Order, Vehicle, Arc, Policy)
- **`simulator/`**: Motor de simulação temporal
- **`tests/`**: Testes unitários para validação

### Fluxo de Simulação

1. **Inicialização**: Criação de localizações, pedidos, veículos e rede
2. **Execução**: Simulação temporal com política de roteamento
3. **Resultados**: Métricas de performance e estatísticas

## 📊 Exemplo de Saída

```
Resultados da Simulação:
{'served_on_time': 4, 'served_late': 2, 'total_late_minutes': 45}
```

## 🔧 Personalização

### Modificar Política de Roteamento

Edite `models/policy.py` para implementar suas estratégias:

```python
class MinhaPolicy(Policy):
    def choose_actions(self, vehicle, now):
        # Sua lógica de otimização aqui
        pass
```

### Adicionar Novos Cenários

Modifique `main.py` para testar diferentes configurações:

```python
# Cenário com mais veículos
fleet = [
    Vehicle(vehicle_id="V1", capacity=5, start_location="A"),
    Vehicle(vehicle_id="V2", capacity=5, start_location="A"),
    Vehicle(vehicle_id="V3", capacity=3, start_location="B")
]
```

## 🧪 Testes

### Executar Todos os Testes
```bash
python -m pytest tests/
```

### Teste Específico
```bash
python -m pytest tests/test_policy.py -v
```

### Teste com Cobertura
```bash
python -m pytest tests/ --cov=. --cov-report=html
```

## 📈 Métricas de Performance

O sistema calcula automaticamente:

- **Entregas no prazo**: Pedidos entregues antes do deadline
- **Entregas atrasadas**: Pedidos entregues após o deadline
- **Tempo total de atraso**: Soma dos atrasos em minutos

## 🎯 Próximos Passos

1. **Analise o sistema atual** executando `python main.py`
2. **Identifique problemas** na política de roteamento
3. **Implemente melhorias** na classe Policy
4. **Teste suas mudanças** com os testes existentes
5. **Documente suas decisões** e resultados

## 📚 Recursos Adicionais

- **`DESAFIO_LOGISTICA.md`**: Documento completo do desafio
- **`pytest.ini`**: Configuração dos testes
- **`run_tests.py`**: Script alternativo para execução de testes

## 🤝 Suporte

Para dúvidas sobre o sistema ou implementação, consulte:
- Documentação das classes no código
- Testes unitários como exemplos de uso
- Documento do desafio para contexto completo

---

**Boa sorte na otimização do sistema logístico!** 🚀 