---
layout: post
title: Linux Mint Debian Edition su Dell Xps Studio
tags: []
categories: it
---

(preamble: I do many things over the web every day, search for solutions, find solutions, implement solutions… then I forget everything. So some posts like this are just a collection of things for future memory)

Avevo già provato a installare LMDE sul mio portatile, ma mi dava kernel panic all’avvio. Facendo partire la modalità “compatibility mode” la live invece si avvia. Ho guardato un po’ le opzoni al boot che ha questa modalità…

**Soluzione:**
Se avete una Mint o una LMDE che va in kernel panic all’avvio provate aggiungendo nelle opzioni di boot

    acpi=off

Installate LMDE e poi avviatela dal vostro disco ricordandovi di nuovo di aggiungere questa opzione tra le opzioni di boot. Installate i drivers nvidia e generate il file di configurazione con nvidia-xconfig. RIavviate… ma NON mettete l’opzione acpi=off perché altrimenti non verrà rilevato il display e non partirà X. L’opzione corretta da mettere è

    noapic

Dovrebbe funzionare.
