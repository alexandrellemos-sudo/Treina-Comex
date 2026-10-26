# Landing Treina Comex (treinacomex.com.br)

Site estático: um `index.html` com as imagens em `img/` e o vídeo em `video/`. Não precisa de build.

## Antes de colocar no ar (obrigatório)
- [ ] **Formulários:** ainda mostram "Prévia do formulário". Ligar ao Supabase/CRM e mandar o PDF do guia depois do cadastro.
- [ ] **PDF do guia:** hospedar o arquivo e liberar o download após o cadastro.
- [ ] Conferir a autorização de imagem das fotos e dos depoimentos.

## Publicar
1. Criar um repositório no GitHub (ex.: `treinacomex-landing`) e enviar o conteúdo desta pasta (`index.html`, `img/`, `video/`, `vercel.json`, `robots.txt`, `sitemap.xml`, `favicon.png`, `apple-touch-icon.png`, `og-image.png`).
2. No Vercel: Add New > Project > importar o repositório. Framework Preset: **Other**. Build command e output directory: deixar vazios. Deploy.
3. Testar no endereço provisório `*.vercel.app` (computador e celular, links e vídeos).
4. Trocar o domínio (só depois do passo 3 aprovado):
   - No Lovable (projeto do marketplace > Settings > Domains): remover `treinacomex.com.br` e `www.treinacomex.com.br`. Manter `cursos.treinacomex.com.br`.
   - No Vercel (Project > Settings > Domains): adicionar `treinacomex.com.br` e `www.treinacomex.com.br` (o www redireciona para o raiz).
   - No provedor de DNS: seguir os registros que o Vercel mostrar (normalmente A `76.76.21.21` para o raiz e CNAME `cname.vercel-dns.com` para o www). Não mexer nos registros MX (e-mail).
5. Conferir: `treinacomex.com.br` abre a landing; `treinacomex.com.br/courses` redireciona para `cursos.treinacomex.com.br/courses`.

## Redirecionamentos
O `vercel.json` já redireciona os endereços antigos do marketplace (cursos, login, páginas de treinamento, área do aluno e admin, páginas legais, links de compartilhamento) para `cursos.treinacomex.com.br`, para não quebrar links já divulgados.

## Depois
- Atualizar no Supabase (Auth) o Site URL e os redirect URLs para `https://cursos.treinacomex.com.br`.
- Atualizar no Stripe os endereços de retorno e webhooks.
- Atualizar o domínio nos e-mails automáticos, no bot de WhatsApp e no código do marketplace (index.html, sitemap, robots, canonical).
- Cadastrar o domínio raiz no Google Search Console e enviar o `sitemap.xml`.
