---
header-includes:
  - \usepackage{upgreek}
  - \usepackage{txfonts}
  - \usepackage{mathtools}
  - \usepackage{braket}
  - \usepackage{amsmath}
  - \usepackage{multicol}
  - \usepackage{xcolor}
  - \usepackage{gensymb}
  - \usepackage[utf8]{inputenc}

fontsize: 8pt
interlinespace: 4ex
whitespace: small
title: Network theory reveals how multilinkers and motors reshape actomyosin
author: Yossi Eliaz
subtitle: Cheung Lab, University of Houston
date: "APS, March 2020"
---

# Actomyosin dynamics is crucial for a living cell to function
:::::::::::::: {.columns}
::: {.column width="50%"}
- Cell division and cytokinesis
- Cell migration
- Muscle contraction
- Tissue morphogenesis
- Vesicle and organelle movement
- Cell signaling
- \textcolor{red}{Synaptic regulation in neurons during long-term potentiation (LTP) and long-term depression (LTD)}

:::
::: {.column width="50%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\Actomyosin networks gardel nature review.png){ height=400px }


![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\Memory formation.png){ height=400px }
:::
::::::::::::::

###### References:
*Cingolani, et al. Nature Reviews Neuroscience 2008*

*Murrell, et al. Nature reviews Molecular cell biology 2015*

*Okamoto, et al. PNAS 2007*

# Actomyosins are active matter using molecular fuel ATP
:::::::::::::: {.columns}
::: {.column width="50%"}
- Motors Regulate the Morphologies of Actomyosin networks in Experiments which used light to spatiotemporally control motor activity and the actomyosin network morphologies. 

- Actin Filaments (F-actin) grow from the polymerization of G-actin monomers occurs over three phases: a nucleation phase, an elongation phase and a steady state phase.
:::
::: {.column width="50%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\Polymerization.png){ height=400px }


![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\actomyosin motor activity.PNG){ height=150px }
$\textbf{Scale bar: } 25 \upmu \textrm{m}$

:::
::::::::::::::

###### References:
*Cingolani, et al. Nature Reviews Neuroscience 2008*

*Linsmeier, et al. Nature communications 2016*

*Lodish, et al. Molecular Cell Biology 2000*

<!--
Manual
https://pandoc.org/MANUAL.html
-->

# Actomyosin network simulations consider only up to bivalent ($\nu \le 2$) actin-binding and actin-related proteins
:::::::::::::: {.columns}
::: {.column width="50%"}
- The Arp2/3 complex nucleates a branched daughter filament from a preexisting mother filament at a distinctive $70 \degree$ angle
- The $\alpha$-actinin protein is a bivalent crosslinker ABP
- The Myosin motor protein that can walk along filaments and exert force
- The polymerization regulating proteins (Formin, Ena/VASP, and capping proteins) 
:::
::: {.column width="50%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\medyan.PNG){ height=200px }
:::
::::::::::::::

###### References:
*Nedelec, et al. New Journal of Physics 2007*

*Popov, Komianos, and Papoian, PLoS computational biology 2016*

*Freedman, Dinner, et al. Biophysical journal 2017*

# We incorporate multilinker ($\mu \ge 2$) ABPs into Cytosim
- CaMKII($\textrm{Ca}^{2+}$/calmodulin-dependent kinase) is a multilinker ABP
- CaMKII is crucial for the maintenance of long-term memory
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\model with multilinker.PNG){ height=200px }

# The chemical reactions of the crosslinkers, motors, filaments, and \textcolor{red}{multilinkers} in Cytosim
 $$\mathrm{F}^{n}\mathrm{CL} + \mathrm{F} \xrightleftharpoons[k_{on}^{CL}]{k_{off}^{CL}} \mathrm{F}^{n+1}\mathrm{CL}  \quad \textrm{where} \quad n\in \Set{0,1}$$
 $$\mathrm{F}^{n}\mathrm{ML}_\nu + \mathrm{F} \xrightleftharpoons[k_{on}^{ML}]{k_{off}^{ML}} \mathrm{F}^{n+1}\mathrm{ML}_\nu  \quad \textrm{where} \quad n\in \Set{0,1,...,\nu = \textrm{multilinker's max valency}} $$
 $$\mathrm{F}^{n}\mathrm{Motor} + \mathrm{F} \xrightleftharpoons[k_{on}^{Motor}]{k_{off}^{Motor}} \mathrm{F}^{n+1}\mathrm{Motor}$$

  | Parameter | Description  | values  |
  |:------------------:|:-----------------------------:|-----------------:|
  |   $k_{off}^{CL}$          | Crosslinker Unbinding Rate           | $0.1 \textrm{s}^{-1}$|
  |   $k_{on}^{CL}$          | Crosslinker Binding Rate           | $5 \textrm{s}^{-1}$|
  |   $k_{off}^{ML}$          | Multilinker Unbinding Rate           | $0.1 \textrm{s}^{-1}$|
    |   $k_{on}^{ML}$          | Multilinker Binding Rate           | $5 \textrm{s}^{-1}$|
  |   $k_{on}^{Motor}$          | Motor Unbinding Rate             | $0.1 \textrm{s}^{-1}$|
  |   $k_{off}^{Motor}$          | Motor Binding Rate            | $10 \textrm{s}^{-1}$|

###### References:
*Nedelec, et al. New Journal of Physics 2007*

*Wang, Cheung, et al. PNAS 2019*

# The parameter space explored in the multilinker simulations in Cytosim
  | Parameter | Description  | values  |
  |:------------------:|:-----------------------------:|:-----------------:|
  |   $\nu$          | \textcolor{red}{Multlinker} valency            | $\{2,3,4,5,6,7\}$|
  | $N_{filaments}$  | Number of filaments in the system      |  $\{250, 500, 1000\}$ |
  | $N_{motors}$     | Number of motors in the system         |  $\{10, 250, 500, 1000\}$ |
  | $N_{crosslinkers}$     | Number of $\alpha$-actinin in the system            | $\{10, 250, 500, 1000\}$ |
  | $N_{multilinkers}$     | Number of multilinkers in the system            | $\{10, 250, 500, 1000\}$ |
  | $V_{box}$     | Volume of the simulation box | $1 \upmu m^3$ |

###### References:
*Nedelec, et al. New Journal of Physics 2007*

# Multilinker's Valency ($\nu > 2$) Changes the Emerged Morphologies of Actomyosin Networks
$\textrm{Simulations at a 1} \upmu m^3 \textrm{ box}$

![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Multivalent Linkers in Actomyosin Networks\Figures AI\Cytosim Simulations\Cytosim Result Figure.v1.jpg){ height=280px }

# Acto-ring morphologies appear in the presence of heptalinkers ($\nu=7$)

- Motors promote metastable actorings and contract bundle meshes.
- Multilinkers promote bundle meshes of actin filaments.

:::::::::::::: {.columns}
::: {.column width="50%"}

![Steady state bundle mesh](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\Mesh of Bundles low Motor valency 5.png){ height=150px }
:::
::: {.column width="50%"}
![Metastable actoring](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\Valency7 AM Ring.png){ height=150px }
:::
::::::::::::::

###### References:
*Nedelec, et al. New Journal of Physics 2007*
*Eliaz, et al., and Cheung, PRE 2020*



# The order parameters in used to analyze the multilinker role in actomyosin morphogenesis
1. Order parameters that describe the shape and distribution of actin monomers in space. These are derived from the tensor of inertia of the filaments $T_{\alpha \beta} (t) = \frac{1}{2N^2} \Sigma_{i,j=0}^N (r_{i\alpha}(t) - r_{j \alpha}(t)) (r_{i \beta} (t) - r_{j \beta} (t))$. 
2. Gelation of actin filaments into clusters governed by actin-binding proteins (ABPs) such as motors, multilinkers, and crosslinkers. These order parameters allows us to study the second order phase transition of actomyosin networks as active gels in the presence of multilinkers/hubs. This order parameters are computed by knowing the microscopical connectivity between the filaments.
3. Lastly, order parameters based on network theory allows us to explore a complicated dynamics of active bundles, active gels, and active condensed gels. Moreover, in order to calculate the order parameters from network theory there is no need to account the molecular connectivity of the ABPs to the filaments.

# Network theory is sensitive to changes in the gel and takes into account how well connected actin clusters are

:::::::::::::: {.columns}
::: {.column width="40%"}
Although gelation order parameters capture the dynamics of number of clusters, if the network is a gel it can’t differentiate between intra morphologies of the gel clusters. This is why network theory characterizes richer order parameters. Building the adjacency of undirected graph between the filaments allows us to introduce order parameters from graph/network theory and understand the emerged actomyosin networks morphologies.

$$ G = (V,E)$$
where the nodes $V$ are the filaments and an edge $e_{i,j} \in E$ exist between two filaments $i,j$ if there distance is less than $200 \textrm{nm}$.
:::
::: {.column width="60%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Multivalent Linkers in Actomyosin Networks\Figures AI\Graph Order Parameters\Correlation Order Param v.1.jpg){ height=300px }
:::
::::::::::::::

# Fluctuations in the eigenvalues of the moment of inertia tensor show the structural active modes of the actomyosin networks
**The moment of inertia tensor**: 

$$T_{\alpha \beta} (t) = \frac{1}{2N^2} \Sigma_{i,j=0}^N (r_{i\alpha}(t) - r_{j \alpha}(t)) (r_{i \beta} (t) - r_{j \beta} (t))$$

Using its eigenvalues we define the Radius of gyration $R_g(t)$, the asphericity measure $\Delta(t)$, and the shape parameter $S(t)$ to study the modes of fluctuations in actomyosin networks.


$$R_g(t) = \sqrt{\sum_{i=1}^{3} \lambda_i(t)}$$
$$S(t) = \frac{3}{2} \frac{\sum_{i=1}^3(\lambda_i (t))-\overline{\lambda(t)})}{ tr T(t)^3}$$
$$\Delta(t) = \frac{\Pi_{i=1}^3(\lambda_i (t))-\overline{\lambda(t)})}{tr T(t)^2}$$

###### References:
*Dima and Thirumalai, The Journal of Physical Chemistry B 2004*

# The Power Densities of $R_g(t)$, $S(t)$ and $\Delta(t)$
:::::::::::::: {.columns}
::: {.column width="30%"}
We calculate the power density of $R_g(t)$, $S(t)$ and $\Delta(t)$ in two regimes: high and low motor activity. $S(t)$ carries 30dB more power density than $R_g$, and $\Delta(t)$ carries 20dB more power density than $R_g$. High motor activity shifts the power density profile by 20dB.
:::
::: {.column width="70%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Multivalent Linkers in Actomyosin Networks\Figures AI\PSD figure\PSD figure.v3.jpg){ height=260px } 
:::
::::::::::::::

# Multivalency $\nu \ge 3$ promote larger gel cluster

:::::::::::::: {.columns}
::: {.column width="40%"}
- We account for the connectivity between filaments
- If two filaments are connected with a motor, a multilinker, or a cross-linker they form a cluster
- Higher valency multilinker promote larger gelated networks
:::
::: {.column width="60%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Multivalent Linkers in Actomyosin Networks\Figures AI\Gelation Order Parameters\Gelation figure part1.v2.jpg){ height=210px }
:::
::::::::::::::

# Network theory expose a second phase transition after gelation using the graph density order parameter

:::::::::::::: {.columns}
::: {.column width="50%"}

The network theory order parameters expose new phases when there is high motor activity. We call it bundle arborization of clusters in actomyosin networks. Such an order parameter is the graph density, $D(\mathbf{G})$, which varies as a function of the multilinker agents' valency and the concentration of motors in the system. $$D(\mathbf{G}) = \frac{2|E|}{|V|\,(|V|-1)}$$
:::
::: {.column width="50%"}
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Multivalent Linkers in Actomyosin Networks\Figures AI\Graph Order Parameters\Density.v1.jpg){ height=300px }
:::
::::::::::::::

# Acknowledgments
- Cheung Lab
- CTBP Memory Focus Group
- Francois Nedelec
- Past and Present CTBP Members

![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Multivalent Linkers in Actomyosin Networks\Figures AI\Cytosim Simulations\Cytosim Result Figure.v1.jpg){ width=150px }
![](C:\Users\bazoo\Dropbox (Personal)\Yossi Eliaz Manuscripts\Talks\Cheung GM Jan 2020\cheung group.PNG){ width=200px }


# Source code:

```python
from sklearn.neighbors import KernelDensity
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
x = np.random.randn(1000)
x_d = np.linspace(min(x), max(x), 2000)

# instantiate and fit the KDE model
kde = KernelDensity(bandwidth=1.0, kernel='gaussian')

kde.fit(x[:, None])

# score_samples returns the log of the probability density
logprob = kde.score_samples(x_d[:, None])

plt.fill_between(x_d, np.exp(logprob), alpha=0.5)
plt.plot(x, np.full_like(x, -0.01), '|k', markeredgewidth=1)
plt.plot(x_d, -logprob)
```