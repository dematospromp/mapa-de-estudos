# Logic Academy

Organizador de estudos: triagem do aluno (colégio, vestibular, concurso, faculdade), plano semanal, pomodoro, banco de questões oficiais, catálogo de provas de todo o Brasil e leitura de editais em PDF.

Site: https://dematospromp.github.io/mapa-de-estudos/

## Arquivos
- `index.html`: o site.
- `firebase-config.js`: liga o login com Google/Apple e a nuvem. Enquanto estiver `null`, o site funciona como visitante.
- `firestore.rules`: regras de segurança para colar no Firestore.
- `manifest.webmanifest` e `icones/`: nome e ícone do app quando ele é adicionado à tela inicial.
- `sw.js`: mostra a notificação do alarme do pomodoro no celular (não guarda páginas em cache).
- `questoes/`: banco de questões (provas oficiais do ENEM 2009–2023, INEP, obtidas pela API ENEM em enem.dev), um arquivo por área, com matéria e tópico identificados automaticamente.

## Ativar as contas por e-mail (gratuito)
1. Crie um projeto em https://console.firebase.google.com (plano Spark, gratuito).
2. Em **Authentication → Método de login**, ative **E-mail/senha**.
3. Em **Firestore Database**, crie o banco e cole o conteúdo de `firestore.rules` na aba **Regras**.
4. Em **Configurações do projeto → Seus apps**, crie um app da Web e copie o objeto `firebaseConfig` para `firebase-config.js`.

Opcional: para mostrar também o botão "Entrar com Google", ative o provedor Google, adicione `dematospromp.github.io` em **Authentication → Configurações → Domínios autorizados** e acrescente `google: true` ao objeto em `firebase-config.js`.

## Desafios conferidos pelo servidor

XP, nível, itens e resgates ficam nas coleções `conquistas/{uid}` e `resgates/{uid}/itens/{id}`. As regras em `firestore.rules` conferem cada resgate:

- a tabela oficial de XP e itens (`defs()`), que precisa ser igual à `DEF_SRV` do site;
- o período (dia, semana e mês no horário de Brasília, pela hora do servidor);
- o tempo de estudo que o próprio servidor registrou no `ranking` nesse período;
- um resgate por desafio e período, sem apagar nem editar depois.

O perfil público só aceita molduras, capas, títulos, emblemas e nível que estejam em `conquistas/{uid}`. Sempre que mudar as regras, cole o arquivo inteiro de novo no console do Firebase.
