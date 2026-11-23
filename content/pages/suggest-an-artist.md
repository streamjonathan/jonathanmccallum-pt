---
title: "Sugerir um artista"
slug: suggest-an-artist
---

Adoro conhecer músicos e artistas que seguem Jesus. Se conhece alguém sobre quem devo escrever, entrevistar ou fazer um vídeo de reação, diga-me aqui.

Um nome e um link bastam — e umas palavras sobre porquê essa pessoa. Leio tudo o que chega. Muito obrigado.

Conhece alguém? Toque na foto e o formulário preenche-se sozinho — depois acrescente umas palavras sobre porquê essa pessoa e envie.

<div class="suggest-carousel" role="list" aria-label="Músicos e artistas que pode sugerir">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="Sugerir {{ artist.name }}">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">Ou sugira alguém novo abaixo — qualquer pessoa que ache que devo conhecer.</p>

Este site não é para pessoas com menos de 18 anos.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Nome do artista</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="Quem devo conhecer?" required>

  <label for="suggest-link">Link do perfil nas redes sociais</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>O que faço com essa pessoa?</legend>
    <label><input type="checkbox" name="kind" value="write"> Escrever sobre essa pessoa</label>
    <label><input type="checkbox" name="kind" value="interview"> Entrevistar essa pessoa</label>
    <label><input type="checkbox" name="kind" value="reaction"> Fazer um vídeo de reação sobre essa pessoa</label>
  </fieldset>

  <label for="suggest-why">Porquê essa pessoa?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Umas palavras bastam…"></textarea>

  <label for="suggest-name">O seu nome <span class="optional">(opcional)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Para lhe poder agradecer">

  <label for="suggest-from-link">Link do seu perfil nas redes sociais <span class="optional">(opcional)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Enviar sugestão</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
