 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index 15d3a89bb7545f63133f025b9779a8aab87212ca..4004b561a5be594cc84664033b2d0776d960fa59 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,48 @@
-# Brito
\ No newline at end of file
+# Brito Saúde — Site Profissional (funcionando)
+
+Repositório com o novo site institucional estático da **Brito & Associados**, pronto para rodar localmente e publicar no GitHub Pages.
+
+## Estrutura
+
+- `index.html`: página institucional completa com hero, atuação, corpo técnico, compliance e contato.
+- `styles.css`: estilos responsivos (desktop/mobile), tipografia, cards e CTA.
+- `.github/workflows/deploy-pages.yml`: deploy automático no GitHub Pages.
+- `.github/workflows/ci-validate.yml`: validação para evitar erro de colar patch no lugar de CSS/HTML.
+- `scripts/validate-static.sh`: valida referências e integridade dos arquivos estáticos.
+
+## Como executar localmente
+
+### Opção rápida
+Abra `index.html` no navegador.
+
+### Opção recomendada (simula produção)
+```bash
+python3 -m http.server 8080
+```
+Depois acesse: `http://127.0.0.1:8080`.
+
+## Como testar no GitHub (GitHub Pages)
+
+1. Faça push deste repositório para o GitHub.
+2. No GitHub, abra **Settings → Pages**.
+3. Em **Build and deployment**, selecione **Source: GitHub Actions**.
+4. Vá na aba **Actions** e aguarde:
+   - `Validate static site files`
+   - `Deploy static site to GitHub Pages`
+5. Acesse a URL pública:
+   - `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`
+
+> Observação: os workflows disparam em push para `main`, `master` e `work`.
+
+## Verificação local rápida
+
+```bash
+bash scripts/validate-static.sh
+```
+
+## Próximas evoluções
+
+1. Subir imagens oficiais da marca e da equipe.
+2. Integrar formulário real de contato (e-mail/CRM/WhatsApp).
+3. Adicionar SEO avançado (Open Graph, sitemap e schema.org).
+4. Criar páginas extras: Sobre, Serviços detalhados, Blog.
 
EOF
)
