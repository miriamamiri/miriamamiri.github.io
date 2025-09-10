---
layout: single
title: "Reinforcement Learning for Consumer Influence: Pricing, Advertising, and Network Effects"
coauthors: "Ehsan Ardjmand, Ali Tavasoli, Behnaz Moradi-Jamei, Heman Shakeri"
status: "Under 2nd round review"
year: 2025
date: 2025-06-24
areas:
  - "Deep learning"
  - "Network theory"
  - "Firm Strategy"
excerpt: "Firms increasingly rely on both price discounts and advertising campaigns to shape product diffusion in socially connected markets, yet existing models rarely treat these levers jointly or account for network heterogeneity. This study develops an integrated, network-aware framework for dynamic pricing and advertising control. A stochastic compartmental model of the CDM is formulated on a social graph, with transition intensities modulated by price, advertising spend, and peer influence. A deterministic mean-field approximation yields closed-form expressions for a TFE and a reproduction number threshold that delineates when adoption dies out versus persists. 

Building on this analytical core, the paper introduces TD3ES, a RL controller that couples an actor-critic architecture with a graph-convolutional autoencoder, thereby compressing high-dimensional network states into a tractable latent representation. A custom GPU-accelerated simulator facilitates large-scale training. Numerical experiments on Erdős-Rényi and heavy-tailed exponential networks show that TD3ES swiftly converges to profit-maximizing joint policies and, on heterogeneous graphs, outperforms a TD3 baseline that lacks network-structural information. Error analysis reveals that the autoencoder naturally prioritizes high-degree hubs in dominant CDM compartments, explaining its superior performance. Managerially, the results demonstrate that ignoring topology can forfeit substantial revenue and that adaptive, network-aware coordination of price and advertising is both feasible and valuable. The framework thus unites rigorous diffusion theory with scalable learning, offering a practical tool for data-driven marketing in connected consumer ecosystems."
pdf:
#slides:
header:
  teaser: /images/research/rl-network-pricing.png
---
**Status:** {{ page.status }}{% if page.year %} · {{ page.year }}{% endif %}  
{% if page.areas %}**Areas:** {{ page.areas | join: ", " }}{% endif %}  
{% if page.methods %}**Methods:** {{ page.methods | join: ", " }}{% endif %}  
{% if page.coauthors %}**Coauthors:** {{ page.coauthors }}{% endif %}


### Abstract
Firms increasingly rely on both price discounts and advertising campaigns to shape product diffusion in socially connected markets, yet existing models rarely treat these levers jointly or account for network heterogeneity. This study develops an integrated, network-aware framework for dynamic pricing and advertising control. A stochastic compartmental model of the CDM is formulated on a social graph, with transition intensities modulated by price, advertising spend, and peer influence. A deterministic mean-field approximation yields closed-form expressions for a TFE and a reproduction number threshold that delineates when adoption dies out versus persists. Building on this analytical core, the paper introduces TD3ES, a RL controller that couples an actor-critic architecture with a graph-convolutional autoencoder, thereby compressing high-dimensional network states into a tractable latent representation. A custom GPU-accelerated simulator facilitates large-scale training. Numerical experiments on Erdős-Rényi and heavy-tailed exponential networks show that TD3ES swiftly converges to profit-maximizing joint policies and, on heterogeneous graphs, outperforms a TD3 baseline that lacks network-structural information. Error analysis reveals that the autoencoder naturally prioritizes high-degree hubs in dominant CDM compartments, explaining its superior performance. Managerially, the results demonstrate that ignoring topology can forfeit substantial revenue and that adaptive, network-aware coordination of price and advertising is both feasible and valuable. The framework thus unites rigorous diffusion theory with scalable learning, offering a practical tool for data-driven marketing in connected consumer ecosystems.
