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

## 3. Primeiro acesso
1. **Sua esposa cria a conta primeiro**: a primeira conta criada vira **admin** automaticamente.
2. Ela cadastra os clientes em **Cadastros**.
3. Cada técnico abre o link e toca em **Criar conta**. A conta fica "aguardando liberação" até ela tocar em **Liberar**.
4. No celular: menu do navegador → **Adicionar à tela inicial**.

## Como funciona
- **Técnico**: lança o diário (cliente, técnicos, horários, intervalo, serviço, materiais, fotos) e vê só os diários dele ou dos quais participou. Pode editar enquanto não for aprovado; se for reprovado, vê o motivo, corrige e reenvia.
- **Admin**: vê tudo, aprova/reprova, marca como cobrado, tira relatório de horas por cliente (Excel ou PDF) e libera/bloqueia usuários.
- Horas: calculadas sozinhas (fim − início − intervalo). Homem-hora = horas × nº de técnicos.
- Fotos: reduzidas para ~1600 px antes de enviar, para economizar espaço (o plano grátis tem 1 GB).

## Limitações desta primeira versão
- "Esqueci a senha" depende de e-mail. Sem um servidor de e-mail próprio configurado no Supabase (SMTP), ele só funciona para os e-mails da sua conta Supabase.
- Projetos grátis do Supabase são pausados após 7 dias sem uso. Se isso acontecer, é só reativar no painel.
