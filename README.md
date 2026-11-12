<img src="assets/header.svg" width="100%" alt="George Derick | Web Developer" />

<div align="center">

<a href="#projetos"><img src="assets/btn-projetos.svg" height="40" alt="Ver projetos" /></a>
<a href="https://github.com/georgederick"><img src="assets/btn-github.svg" height="40" alt="GitHub" /></a>
<a href="https://georgederick.github.io/portfolio/"><img src="assets/btn-contato.svg" height="40" alt="Portfólio" /></a>

</div>

<img src="assets/marquee.svg" width="100%" alt="HTML5, CSS3, JavaScript, React.js, TypeScript, Tailwind CSS, Git, GitHub, SQL, MySQL, Node.js, Figma" />

<br/>

<img src="assets/sec-sobre.svg" width="100%" alt="Sobre mim" />

<img src="assets/about.svg" width="100%" alt="Formado em Análise e Desenvolvimento de Sistemas pela Faculdade Anhanguera (2025), com curso profissionalizante em Suporte de TI do Google/Coursera. São Paulo – SP." />

<br/>

<img src="assets/sec-habilidades.svg" width="100%" alt="Habilidades" />

<img src="assets/skills.svg" width="100%" alt="Front-End, ferramentas de desenvolvimento, programação e banco de dados, tecnologia da informação e conhecimentos administrativos." />

<br/>

<a id="projetos"></a>
<img src="assets/sec-projetos.svg" width="100%" alt="Projetos" />

<a href="https://georgederick.github.io/Conecta-Tech/"><img src="assets/project-1.svg" width="100%" alt="Conecta Tech" /></a>

<a href="https://georgederick.github.io/Conecta-Tech/"><img src="assets/btn-demo.svg" height="38" alt="Demonstração de Conecta Tech" /></a>
<a href="https://github.com/georgederick/Conecta-Tech"><img src="assets/btn-repo.svg" height="38" alt="Repositório de Conecta Tech" /></a>

<br/>

<a href="https://georgederick.github.io/atlas-mundi/"><img src="assets/project-2.svg" width="100%" alt="Atlas Mundial" /></a>

<a href="https://georgederick.github.io/atlas-mundi/"><img src="assets/btn-demo.svg" height="38" alt="Demonstração de Atlas Mundial" /></a>
<a href="https://github.com/georgederick/atlas-mundi"><img src="assets/btn-repo.svg" height="38" alt="Repositório de Atlas Mundial" /></a>

<br/>

<a href="https://georgederick.github.io/the-golden-pig/"><img src="assets/project-3.svg" width="100%" alt="The Golden Pig" /></a>

<a href="https://georgederick.github.io/the-golden-pig/"><img src="assets/btn-demo.svg" height="38" alt="Demonstração de The Golden Pig" /></a>
<a href="https://github.com/georgederick/the-golden-pig"><img src="assets/btn-repo.svg" height="38" alt="Repositório de The Golden Pig" /></a>

<br/>

<a href="https://georgederick.github.io/Flua/"><img src="assets/project-4.svg" width="100%" alt="Flua" /></a>

<a href="https://georgederick.github.io/Flua/"><img src="assets/btn-demo.svg" height="38" alt="Demonstração de Flua" /></a>
<a href="https://github.com/georgederick/Flua"><img src="assets/btn-repo.svg" height="38" alt="Repositório de Flua" /></a>

<br/>

<a href="https://georgederick.github.io/windows-xp-/"><img src="assets/project-5.svg" width="100%" alt="Windows XP" /></a>

<a href="https://georgederick.github.io/windows-xp-/"><img src="assets/btn-demo.svg" height="38" alt="Demonstração de Windows XP" /></a>
<a href="https://github.com/georgederick/windows-xp-"><img src="assets/btn-repo.svg" height="38" alt="Repositório de Windows XP" /></a>

<br/>

<a href="https://georgederick.github.io/apex-telemetry"><img src="assets/project-6.svg" width="100%" alt="Apex Telemetry" /></a>

<a href="https://georgederick.github.io/apex-telemetry"><img src="assets/btn-demo.svg" height="38" alt="Demonstração de Apex Telemetry" /></a>
<a href="https://github.com/georgederick/apex-telemetry"><img src="assets/btn-repo.svg" height="38" alt="Repositório de Apex Telemetry" /></a>

<br/>

<img src="assets/sec-formacao.svg" width="100%" alt="Formação e cursos" />

<img src="assets/education.svg" width="100%" alt="Bacharelado em ADS (Anhanguera, 2025), Suporte de TI (Google/Coursera, 2024) e cursos complementares." />

<br/>

<img src="assets/sec-github.svg" width="100%" alt="GitHub" />

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=georgederick&show_icons=true&bg_color=121212&border_color=2a2a2a&title_color=ffffff&icon_color=7C83FF&text_color=d4d4d4&ring_color=7C83FF" alt="GitHub Stats" />
<img height="170" src="https://streak-stats.demolab.com?user=georgederick&background=121212&border=2a2a2a&stroke=2a2a2a&ring=7C83FF&fire=7C83FF&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=7C83FF&sideLabels=9a9a9a&dates=9a9a9a" alt="GitHub Streak" />

</div>
name: generate pacman contribution graph

on:
  schedule:
    - cron: "0 */12 * * *"   # atualiza a cada 12 horas
  workflow_dispatch:          # permite rodar manualmente
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 5
    steps:
      - name: Generate pacman-contribution-graph.svg
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}

      - name: Push SVGs to the output branch
        run: |
          cd dist
          git init -b output
          git config user.name "github-actions[bot]"
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git add .
          git commit -m "chore: update pacman contribution graph"
          git remote add origin "https://x-access-token:${{ secrets.GITHUB_TOKEN }}@github.com/${{ github.repository }}.git"
          git push -f origin output

<!-- Se quiser manter o seu Pac-Man de contribuições, cole o bloco dele aqui -->

<br/>

<img src="assets/sec-contato.svg" width="100%" alt="Contato" />

<p align="center">
  <a href="mailto:georgederickk@gmail.com"><img src="assets/contact-email.svg" width="49%" alt="E-mail" /></a>
  <a href="tel:+5511953706785"><img src="assets/contact-phone.svg" width="49%" alt="Telefone" /></a>
  <a href="https://www.linkedin.com/in/georgederick/"><img src="assets/contact-linkedin.svg" width="49%" alt="LinkedIn" /></a>
  <a href="https://github.com/georgederick"><img src="assets/contact-github.svg" width="49%" alt="GitHub" /></a>
  <img src="assets/contact-local.svg" width="49%" alt="São Paulo – SP, Brasil" />
</p>

<p align="center">
  <a href="https://georgederick.github.io/portfolio/curriculo-george-derick.pdf"><img src="assets/btn-curriculo.svg" height="40" alt="Baixar currículo (PDF)" /></a>
</p>

<img src="assets/footer.svg" width="100%" alt="© 2026 Georgederick · Web Developer" />
