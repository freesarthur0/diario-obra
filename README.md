# Diário de Obra — como colocar no ar

## Arquivos
- `index.html` — o app inteiro (login, técnico e admin)
- `manifest.webmanifest` e `icon.svg` — permitem "instalar" na tela inicial do celular

O banco já está criado no Supabase (projeto **Diario de Obra**, região São Paulo).

## 1. Ajuste no Supabase (uma vez só)
Painel do Supabase → projeto **Diario de Obra** → **Authentication**:
1. Em **Sign In / Providers → Email**, desligue **Confirm email**.
   (O e-mail padrão do Supabase só entrega para os membros da sua conta Supabase, então os técnicos não receberiam a confirmação.)
2. Em **URL Configuration**, coloque `https://freesarthur0.github.io/diario-obra/` em **Site URL**.

## 2. Publicar (GitHub Pages, grátis)
1. No repositório: **Settings → Pages → Deploy from a branch → `main` / `/ (root)`** → Save.
2. Endereço: https://freesarthur0.github.io/diario-obra/
3. Cada novo commit na `main` atualiza o site sozinho.

## 3. Uso
- Hoje **só a admin usa o app** e preenche os diários no lugar dos técnicos.
- **Colar do WhatsApp:** em "Novo", cole a mensagem do diário (ou várias de uma vez) e toque em "Preencher o formulário". O app reconhece Data, Cliente, Técnico(s), Horário, Intervalo, Serviço executado e Material utilizado. Se aparecer cliente ou técnico que ainda não existe, ele oferece cadastrar com um toque.
- **Técnicos** são um cadastro simples (só o nome), em Cadastros. Não precisam de login.
- Diário lançado pela admin já fica **aprovado**.
- Horas: calculadas sozinhas (fim − início − intervalo). Homem-hora = horas × nº de técnicos.
- Fotos: reduzidas para ~1600 px antes de enviar, para economizar espaço (o plano grátis tem 1 GB).
- Se um dia os técnicos forem lançar os próprios diários: eles criam a conta pela tela de login e a admin libera em Cadastros → Acesso ao app.

## PDFs
- O PDF do diário e o do relatório saem na **folha timbrada** (`timbrado.jpg`, montada a partir do modelo .docx da empresa), em todas as páginas.
- Para trocar a folha timbrada, basta substituir o `timbrado.jpg` (A4 em pé, 1654 × 2339 px).

## Limitações desta primeira versão
- "Esqueci a senha" depende de e-mail. Sem um servidor de e-mail próprio configurado no Supabase (SMTP), ele só funciona para os e-mails da sua conta Supabase.
- Projetos grátis do Supabase são pausados após 7 dias sem uso. Se isso acontecer, é só reativar no painel.
