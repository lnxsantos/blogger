---
title: "Meu laboratório de estudos em cibersegurança: ThinkPad X230, Fedora e a importância de documentar"
date: 2025-11-23
draft: false
categories:
  - "Cybersecurity"
  - "Forensics"
  - "Linux"
  - "Learning"
tags:
  - "ThinkPad"
  - "Fedora"
  - "Hardening"
  - "TryHackMe"
  - "HackTheBox"
  - "CTF"
  - "OSINT"
  - "Linux Security"
  - "Forense Digital"
description: "Como montei meu laboratório de estudos com ThinkPad X230 e Fedora, e por que documentar é essencial quando se estuda cibersegurança sozinho. Hardening, CTFs e preparação para Perito Forense Digital da PF."
keywords:
  - "estudante de cibersegurança"
  - "jornada na cibersegurança"
  - "tryhackme"
  - "hack the box"
  - "ctf hardening"
  - "thinkpad x230"
  - "fedora security"
  - "linux hardening"
  - "osint"
  - "laboratório de segurança"
image: "/images/posts/jornada-cyber.png"
level: "Intermediário"
---

Estudar cibersegurança enquanto trabalho como programador não é fácil. O tempo é limitado, os conceitos são complexos e, quando você finalmente entende algo, semanas depois já esqueceu os detalhes importantes.

Foi exatamente isso que me fez perceber a importância de documentar. Não apenas anotar, mas realmente escrever, organizar e consolidar o conhecimento de forma que eu pudesse voltar depois e entender rapidamente o que fiz, por que fiz e como fiz.

## A dificuldade de estudar sozinho

Quando comecei a estudar cibersegurança de forma séria, enfrentei alguns desafios:

* **Volume de informação**: Hardening em Linux, análise forense, investigação digital, técnicas de segurança — são muitos tópicos diferentes e cada um exige tempo e prática.

* **Falta de contexto**: Muitas vezes eu aprendia algo, mas não documentava o contexto. Duas semanas depois, não lembrava mais por que tinha feito determinada configuração ou qual problema estava resolvendo.

* **Erros repetidos**: Sem documentar, eu acabava cometendo os mesmos erros várias vezes. Perdia tempo refazendo o que já tinha feito antes.

* **Falta de referência**: Quando precisava revisar algo, não tinha uma referência organizada. Tudo estava espalhado em notas, arquivos e memória.

Foi então que percebi: **documentar não é opcional, é essencial para quem estuda sozinho**.

## Por que este blog existe

Este blog tem dois propósitos principais:

**a)** Consolidar meu aprendizado. Cada técnica que aprendo, cada ferramenta que uso, cada erro que cometo — tudo isso vira conteúdo aqui. É uma forma de criar uma referência para mim mesmo e garantir que o conhecimento não se perca.

**b)** Acompanhar minha preparação para o concurso de Perito Forense Digital da Polícia Federal. Vou compartilhar estudos, metodologias, ferramentas e tudo que estou aprendendo nessa jornada.

Se você está começando em cibersegurança ou também está se preparando para concursos na área, espero que este espaço seja útil. E se você já tem experiência, adoraria trocar conhecimentos.

## Meu Laboratório de Estudos

Trabalhando como programador, meu dia a dia sempre foi código, APIs, lógica de negócio. Mas quando comecei a estudar cibersegurança, percebi que precisava ir além — queria entender sistemas de verdade, redes de verdade, segurança de verdade.

Então montei meu próprio laboratório. Um espaço onde posso testar, quebrar, aprender e errar sem medo.

É aqui que eu:

* estudo kernel, memória, processos e permissões
* testo vulnerabilidades e técnicas de segurança
* pratico hardening e vejo as consequências reais
* analiso tráfego de rede e protocolos
* treino forense digital e investigação
* aprendo fazendo, não só lendo

Foi o melhor investimento que fiz na minha preparação.

## Meu Setup: ThinkPad X230 + Fedora Linux

{{< case title="Meu Setup Principal" impact="Laboratório de estudos pessoal" date="2024" >}}
ThinkPad X230 rodando Fedora Linux — minha estação de trabalho e laboratório de estudos em um só dispositivo.
{{< /case >}}

### Por que escolhi o ThinkPad X230?

Precisava de uma máquina que eu não tivesse medo de abrir, desmontar, resetar e arriscar. Como programador, meu computador principal não podia ser meu laboratório de erros. O X230 virou esse espaço livre.

**Vantagens para alguém como eu — programador de dia, estudante de segurança à noite:**

* fácil de desmontar e modificar
* modular e resistente
* compatível com praticamente qualquer distro Linux
* perfeito para estudar hardware e firmware
* preço acessível para um laboratório dedicado

O X230 não é só um notebook usado. Ele virou meu laboratório físico.

### Por que Fedora? Por que não Kali ou Parrot?

Como programador, nunca quis um sistema que me desse tudo pronto. Queria construir meu entendimento com as próprias mãos.

Por isso escolhi Fedora: queria sentir a estrutura real de um sistema Linux moderno. Queria trabalhar com SELinux, systemd, journald, políticas, initramfs, módulos — coisas que não aparecem no meu trabalho diário, mas que são exatamente o que preciso aprender para o concurso.

Fedora me obriga a:

* entender o SELinux a fundo
* trabalhar com systemd e suas units
* ajustar journald para auditoria
* configurar firewall manualmente
* instalar ferramentas sem presets
* lidar com kernel moderno e patches recentes

É mais difícil? Sim. Mas também é o que me faz aprender de verdade.

Quando algo quebra, eu sei que fui eu quem quebrou. E isso é libertador.

## Criptografia de Disco: Onde Aprendi Que Segurança Tem Custo

Quando configurei LUKS2 com Argon2id, achei que estava “fazendo tudo certo”. Até perceber que o boot estava levando **4 minutos** só para derivar a chave.

A solução veio com estudo, teste, benchmark e ajustes.

Hoje entendo:

* o que é uma função memory-hard
* como funciona a derivação da chave
* quando trocar velocidade por segurança
* quando isso é exagero

E principalmente:

> segurança sem equilíbrio vira dor de cabeça.

## Hardening: Meu Aprendizado Mais Profundo

Como programador, nunca tinha precisado pensar em `/etc/fstab`, mount flags, initramfs ou permissões de kernel. Mas quando comecei hardening no meu laboratório, foi inevitável.

Aprendi:

* como ASLR funciona na prática
* como o kernel aplica Lockdown Mode
* por que `noexec` em `/tmp` bloqueia muita coisa
* que SELinux não é um inimigo — é um professor

Passei dias quebrando ferramentas, restaurando permissões, lendo logs enigmáticos como:

```
avc: denied { read write } for pid=1337 comm="python" ...
```

E cada linha dessas me ensinou mais do que um curso inteiro.

## Aprendendo Redes e Wi-Fi: Meu Ponto de Virada

A primeira vez que capturei tráfego real com `tcpdump`, percebi o abismo entre teoria e prática.

Passei semanas:

* analisando handshakes WPA2
* capturando beacon frames
* estudando tráfego em modo monitor
* entendendo 802.11 frame por frame
* usando `airodump-ng`, `kismet`, `bettercap`

E isso mudou completamente minha visão sobre redes.

## TryHackMe, Hack The Box e CTFs: Meu Ciclo de Aprendizado

Meu ciclo é simples:
**estudo → reproduzo no lab → aplico em CTF → documento**

TryHackMe me deu a base.
Hack The Box me ensinou humildade.
CTFs me ensinaram metodologia.

Hoje minha rotina é:

* trabalhar como programador durante o dia
* estudar cibersegurança à noite
* fazer labs e práticas aos poucos
* documentar tudo no blog

Essa disciplina mudou minha relação com tecnologia.

## Pós-Graduação em Cibersegurança: Conectando a Teoria à Prática

Mesmo trabalhando como programador, decidi dar um passo além e formalizar meus estudos com uma **Pós-Graduação em Cibersegurança pela Acadi-TI, com certificação CEH**. Foi uma escolha focada no meu objetivo: passar no concurso de Perito Forense Digital da PF.

Minha vida hoje é assim:

* trabalho como programador durante o dia
* estudo cibersegurança à noite e nos fins de semana
* quando sobra tempo, mergulho no meu laboratório para praticar
* documentar tudo aqui no blog

Esses mundos não competem — eles se complementam. Cada conhecimento em programação me ajuda a entender melhor segurança, e cada estudo em segurança me torna um programador mais consciente.

## O Que Eu Gostaria De Ter Sabido Antes

Se eu pudesse falar com o Luan que estava começando, eu diria:

* você vai quebrar tudo, e isso é parte do processo
* leia logs antes de reinstalar
* estude o porquê, não só o como
* documente para lembrar
* permita-se ser curioso
* sua profissão não define seus limites técnicos
* foco no objetivo final te mantém motivado

Eu não escolhi segurança apenas como hobby. Escolhi segurança como caminho para meu objetivo profissional.

E isso foi o que mais me transformou.

## Guia Para Iniciantes (Versão Mentor)

* Você vai errar. E isso é bom.
* Escolha uma máquina que você não tenha medo de quebrar.
* Trate o Linux como um organismo real.
* Aprenda a depurar antes de reinstalar.
* Hardening não é copiar comandos da internet.
* SELinux está tentando te ajudar.
* Entenda o boot.
* Evite exageros em criptografia.
* Comece ROP cedo.
* Em CTFs, versão importa.
* Documente tudo.
* Não tenha pressa.
