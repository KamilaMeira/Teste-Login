# 🧪 Testes de Login – Aplicação Web (SauceDemo)

Este documento contém os cenários de teste funcionais e negativos realizados na página de login da aplicação de demonstração:  
https://www.saucedemo.com/

---

## ✔ **CT001 – Login com usuário válido (Positivo)**

### **Passos**
1. Acessar a URL: https://www.saucedemo.com/
2. Preencher o nome de usuário: `standard_user`
3. Preencher a senha: `secret_sauce`
4. Clicar no botão **Login**
5. Clicar no menu e selecionar **Logout**

### **Resultado Esperado**
- Login realizado com sucesso  
- Sistema redireciona para a página **inventory**  
- Logout retorna o usuário para a tela de login

### **Resultado Obtido:** ✔ Passou  

---

## ❌ **CT002 – Login sem preencher campos (Negativo)**

### **Cenário 1 – Clique em Login sem preencher nada**

#### Resultado Esperado
- Sistema deve exibir mensagem de erro:  
  **"Cara triste épica: É necessário nome de usuário."**  
- Campos não preenchidos devem ficar destacados em vermelho  
- Usuário não deve ter acesso ao conteúdo

#### Resultado Obtido: ✔ Passou

---

## **Cenário 2 – Apenas nome de usuário preenchido incorretamente**

### Passos
1. Preencher **username** com valor incorreto  
2. Deixar senha vazia  
3. Clicar em Login  

### Resultado Esperado
- Exibir mensagem: **"Que triste! É preciso uma senha"**  
- Campo senha deve estar destacado em vermelho  
- Não deve permitir login

### Resultado Obtido: ✔ Passou

---

## **Cenário 3 – Apenas nome de usuário correto / senha vazia**

### Resultado Esperado
- Exibir mensagem: **"Que triste! É preciso uma senha."**  
- Apenas o campo de senha deve indicar erro  
- Campo de usuário não deve mostrar erro (segurança)

### Resultado Obtido: ❌ Falhou  

### Observação
- O sistema exibiu erro **em ambos os campos**, causando possível confusão ao usuário.  
- **Defeito registrado.**

---

## **Cenário 4 – Apenas senha incorreta / usuário vazio**

### Resultado Esperado
- Mensagem exibida: **"Cara triste épica: É necessário nome de usuário."**  

### Resultado Obtido: ✔ Passou

---

## **Cenário 5 – Apenas senha correta / usuário vazio**

### Resultado Esperado
- Mesma mensagem de erro anterior:  
  **"Cara triste épica: É necessário nome de usuário."**  

### Resultado Obtido: ✔ Passou

---

## **Cenário 6 – Usuário correto + senha incorreta**

### Resultado Esperado
- Mensagem exibida:  
  **"Que triste: O nome de usuário e a senha não correspondem a nenhum usuário neste serviço."**
- Ícone de erro deve aparecer  
- Ambos os campos devem mostrar erro (segurança)

### Resultado Obtido: ✔ Passou

---

## **Cenário 7 – Usuário incorreto + senha correta**

### Resultado Esperado
- Mesmo comportamento do cenário 6  
- Campos devem indicar erro  

### Resultado Obtido: ✔ Passou

---

# 📌 Conclusão geral dos testes

- A maioria dos cenários funcionou corretamente.  
- **Um defeito foi encontrado no cenário 3**, onde o campo de usuário é marcado como erro mesmo quando está preenchido corretamente.  
- Interface e mensagens de erro funcionam conforme o esperado nos demais cenários.


