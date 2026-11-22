# 🖨️ Controle da Impressora Elgin em C

## 📘 Sobre o projeto

Programa em **linguagem C** que se comunica com a impressora térmica **Elgin i8 / i9** usando a biblioteca da Elgin (`E1_Impressora01.dll`).

O programa pede login, mostra um menu e permite imprimir texto, QR Code, código de barras, cupom SAT, cancelamento SAT, abrir a gaveta de dinheiro e fazer a impressora apitar.

Trabalho da disciplina de Programação em C.

## 📁 Arquivos

| Arquivo | O que é |
|---|---|
| `main.c` | Código do programa |
| `E1_Impressora01.dll` | Biblioteca da Elgin (versão x86 ou x64) |
| `XMLSAT.xml` | XML de teste do cupom SAT |
| `CANC_SAT.xml` | XML de teste do cancelamento SAT |

Todos precisam ficar **na mesma pasta** (raiz do projeto).

## ⚙️ Como compilar e executar

1. Descubra se o seu compilador é 32 ou 64 bits:

   ```
   gcc -dumpmachine
   ```

   | Resultado | Compilador | DLL a usar |
   |---|---|---|
   | `x86_64-w64-mingw32` | 64 bits | pasta **x64** |
   | `mingw32` ou `i686-w64-mingw32` | 32 bits (Code::Blocks) | pasta **x86** |

2. Copie a `E1_Impressora01.dll` certa para a pasta do projeto, junto com os dois XMLs.
3. Ligue a impressora e conecte o cabo USB.
4. Na pasta do projeto, rode:

   ```
   gcc main.c -o impressora.exe
   impressora.exe
   ```

No **Code::Blocks**: crie um projeto *Console application → C*, troque o `main.c` por este, copie a DLL e os XMLs para a pasta do projeto e confira em *Project → Properties → Build targets* se o *Execution working dir* é a pasta do projeto.

## 🔑 Login de teste

- **Usuário:** `admin`
- **Senha:** `1234`

São 3 tentativas. Se errar as 3, o programa fecha.

## 📋 Opções do menu

| Nº | Opção |
|---|---|
| 1 | Configurar conexão |
| 2 | Abrir conexão |
| 3 | Fechar conexão |
| 4 | Imprimir texto |
| 5 | Imprimir QR Code |
| 6 | Imprimir código de barras |
| 7 | Imprimir XML SAT |
| 8 | Imprimir XML de cancelamento SAT |
| 9 | Abrir gaveta (Elgin) |
| 10 | Abrir gaveta |
| 11 | Sinal sonoro |
| 0 | Sair |

Valores para teste na opção 1: tipo `1` (USB), modelo `i9` (ou `i8`), porta `USB`, parâmetro `0`.

> As opções de impressão (4 a 11) só funcionam com a conexão aberta (opção 2).

## 👥 Autores

- (nome do integrante 1)
- (nome do integrante 2)
- (nome do integrante 3)
