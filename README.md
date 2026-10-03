# Mapa de Estudos

Organizador de estudos: triagem do aluno (colégio, vestibular, concurso, faculdade), plano semanal, pomodoro, catálogo de provas de todo o Brasil e leitura de editais em PDF.

Site: https://dematospromp.github.io/mapa-de-estudos/

## Arquivos
- `index.html`: o site.
- `firebase-config.js`: liga o login com Google/Apple e a nuvem. Enquanto estiver `null`, o site funciona como visitante.
- `firestore.rules`: regras de segurança para colar no Firestore.

## Ativar login com Google (gratuito)
1. Crie um projeto em https://console.firebase.google.com (plano Spark, gratuito).
2. Em **Authentication → Sign-in method**, ative **Google**.
3. Em **Authentication → Settings → Authorized domains**, adicione `dematospromp.github.io`.
4. Em **Firestore Database**, crie o banco e cole o conteúdo de `firestore.rules` na aba **Regras**.
5. Em **Configurações do projeto → Seus apps**, crie um app da Web e copie o objeto `firebaseConfig` para `firebase-config.js`.

Login com Apple exige uma conta paga no Apple Developer Program (US$ 99/ano); depois é só ativar o provedor **Apple** no Firebase.
