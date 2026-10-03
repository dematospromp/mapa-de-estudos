# Mapa de Estudos

Organizador de estudos: triagem do aluno (colégio, vestibular, concurso, faculdade), plano semanal, pomodoro, catálogo de provas de todo o Brasil e leitura de editais em PDF.

Site: https://dematospromp.github.io/mapa-de-estudos/

## Arquivos
- `index.html`: o site.
- `firebase-config.js`: liga o login com Google/Apple e a nuvem. Enquanto estiver `null`, o site funciona como visitante.
- `firestore.rules`: regras de segurança para colar no Firestore.

## Ativar as contas por e-mail (gratuito)
1. Crie um projeto em https://console.firebase.google.com (plano Spark, gratuito).
2. Em **Authentication → Método de login**, ative **E-mail/senha**.
3. Em **Firestore Database**, crie o banco e cole o conteúdo de `firestore.rules` na aba **Regras**.
4. Em **Configurações do projeto → Seus apps**, crie um app da Web e copie o objeto `firebaseConfig` para `firebase-config.js`.

Opcional: para mostrar também o botão "Entrar com Google", ative o provedor Google, adicione `dematospromp.github.io` em **Authentication → Configurações → Domínios autorizados** e acrescente `google: true` ao objeto em `firebase-config.js`.
