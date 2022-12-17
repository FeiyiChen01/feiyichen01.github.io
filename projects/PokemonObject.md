---
layout: project
type: project
image: img/og-default-image.jpeg
title: "Pokemon"
date: 2020
published: true
labels:
  - Java
  - GitHub
summary: "A basic Pokémon game I developed for ICS 111."
---

<img class="img-fluid" src="../img/Pokemon.jpeg" alt="poke">

Pokémon is a game that has taken the world by storm. In ICS111 we were asked to make a simple game. I chose Pokémon as my project. As a freshman in CS,
My ability only allows me to make a simple battle page.

The following introduction will give you a general idea of what is included in my Battle page。

<hr>

<pre>
A simple text and image GUI.

Contains buttons to make your own Pokemon and a list of Pokemon that have already been made.

<hr>

<pre>

  /********* label. ************/
   private JLabel lTitle = new JLabel("Make your own Pokemon");
   /********* label. ************/
   private JLabel lMsg = new JLabel("                ");
  /******* button. ****************/
   private JButton bDone = new JButton(" Make Pokemon ");
   /******* button. ****************/
   private JButton bList = new JButton(" List Pokemon");
   
</pre>

<hr>

Users can edit Pokémon nicknames and get random HP and Spices.

<hr>

<pre>

      JLabel nPokemon = new JLabel("New Pokemon");
      JLabel lPokemon = new JLabel("Pokemon available");
      JLabel lSpices = new JLabel("Spices: ");
      JLabel lName = new JLabel("Name: ");
      JLabel lNumber = new JLabel("Number: ");
      JLabel lHP = new JLabel("HP: ");

</pre>

<hr>


</pre>

<hr>

The list has a maximum limit, and after two fighting players have created their Pokémon,
they start a battle with random damage until one player's Pokémon's HP is all equal to zero and the page shows that player 1 or player 2 has won。
