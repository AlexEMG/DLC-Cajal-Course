[![Generic badge](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)](README.md)

# Modern Methods for Quantifying Behaviour (DeepLabCut🐭)

Dear participants, welcome 🙌 to the 2022 edition of the hands-on Neuroscience course [Modern Methods for Quantifying Behavior](https://cajal-training.org/neurokit/behavioural-analysis/)! 
<br/><br/>
Let’s kickstart the week 🚀!

Here you will find all the course material 📚 you will need to complete your project. 

One of the main tools used is DeepLabCut**🐭**, a toolbox for markerless pose estimation of animals. Check it out [HERE](https://github.com/DeepLabCut/DeepLabCut). Don’t forget to stay tuned [@DeepLabCut](https://twitter.com/DeepLabCut)!

This course received much support from the CAJAL Advance Neuroscience Training Programme. Have a look [HERE](https://cajal-training.org/) and follow them [@Cajal_Training](https://twitter.com/Cajal_Training?ref_src=twsrc%5Etfw%7Ctwcamp%5Eembeddedtimeline%7Ctwterm%5Escreen-name%3ACajal_Training%7Ctwcon%5Es1_c13) for updates!

```{warning}
NOTE FOR TEACHING ASSISTANTS!

This page will be updated day-by-day next week! Feel free to contribute by making PRs.

- PLEASE put your name and information in the table below! (this table will then also be used in the CourseOverview!)
- Please check the section "#SECTION-FOR-TAs-(will-be-removed)" for ways to create at this Jupyter book and other information!

```

## Teaching Dream Team 🏆

Thanks to the whole teaching team for putting this together 🎉🎉🎉!

| **Role 🔥**            | **Name 📛**          | **🗺️📍**                 | **GitHub 🛠️** | **Twitter 🐥**   |
|-----------------------|---------------------|------------------------|--------------|-----------------|
| Co - Director 🎖️       | Alexander Mathis    | 🛰️ online               | [GitHub](https://github.com/AlexEMG)| [@TrackingPlumes](https://twitter.com/TrackingPlumes)|
| Co - Director 🎖️       | Danbee Kim          | 🛰️ online               | [GitHub](https://github.com/Taunsquared)| [@taunbot](https://twitter.com/taunbot) |
| Cajal Administrator 📝 | Elena Drosti        | 🛰️ online               |              |                 |
| Teaching Assistant 🦅  | Sofia Minano        | London (UK)            | [GitHub](https://github.com/sfmig)       | [@SofiMinano](https://twitter.com/SofiMinano)   |
| Teaching Assistant 🐭  | Nicole Vissers      | London (UK)            | [GitHub](https://github.com/nicole-vissers)| [@NicoleVissers1](https://twitter.com/NicoleVissers1)|
| Teaching Assistant 🦇  | Jonas Håkansson     | Colorado Springs (USA) | [GitHub](https://github.com/biol-jsh)      | [@ScientistJonas](https://twitter.com/ScientistJonas) |
| Teaching Assistant 🐦  | Neslihan Wittek     | 🛰️ online               | [GitHub](https://github.com/neslihanedes)       | [@taubenmaedel](https://twitter.com/taubenmaedel)   |
| Teaching Assistant 🐭  | Andrada Marica      | 🛰️ online               | [GitHub](https://github.com/andrada08)      | [@andrada_marica](https://twitter.com/andrada_marica) |
| Teaching Assistant 🐭  | Sabrina Benas       | Buenos Aires (ARG)     | [GitHub](https://github.com/sabrinabenas)      | [@Sabrineiitor](https://twitter.com/Sabrineiitor)  |
| Teaching Assistant 🐤  | Cecilia Herbert     | Buenos Aires (ARG)     | [GitHub](https://github.com/ChucklesOnGitHub)       | [@ChuckleScience](https://twitter.com/ChuckleScience) |
| Teaching Assistant 🖥️  | Nirel Kadzo         | Nairobi (KEN)          | [GitHub](https://github.com/kadzon)       | [@Nirelkadzo](https://twitter.com/Nirelkadzo)    |
| Teaching Assistant 🐭  | Zane Mitrevica      | 🛰️ online               |[GitHub](https://github.com/zanemit)       | [@Zanemit](https://twitter.com/Zanemit)       |
| Teaching Assistant 🐀  | Konrad Danielewski  | Warsaw (PL)            | [GitHub](https://github.com/KonradDanielewski)      | [@Nyktofob](https://twitter.com/Nyktofob)      |
| Teaching Assistant 🖥️  | Virginia Palieri    | Munich (DE)            | [GitHub](https://github.com/vpalieri)       |                 |
| Teaching Assistant 🖥️  | Aleksandar Gavric   | 🛰️ online               |[GitHub](https://github.com/alex-gavric)      | [@AcaGavric](https://twitter.com/AcaGavric)     |
| Teaching Assistant 🔬  | Aleksandra Gavriova | Okinawa (JP)           | [GitHub](https://github.com/a-gavrilova)       | [@shura_gav](https://twitter.com/shura_gav)     |

## Acknowledgments

Naturally this material is heavily based on [DeepLabCut's Jupyter book](https://deeplabcut.github.io/DeepLabCut/README.html) as well as [DeepLabCut](https://github.com/DeepLabCut/DeepLabCut) in general. The same license applies.


# SECTION FOR TAs (will be removed):

This section will be removed but for now will be used to share information with you!

## How to build the jupyter book? (this is only required before this repository is public)

Install: `pip install -U jupyter-book`

From the main folder, run the following command: `jupyter-book build .`

## To-dos -- mostly for AM but feel free to help :)

- use jupyter book bibliography for the references in the book, https://jupyterbook.org/en/stable/content/citations.html
- there are a number of TBD items in the document, those are for AM to fix (or maybe you can contribute?)!

## Materials to check out for preparing (probably you know most of those)

### Day 1 (TBD: turn into links, see [here](http://www.mackenziemathislab.org/deeplabcut))

Anderson and Perona [Toward a science of computational ethology](https://www.sciencedirect.com/science/article/pii/S0896627314007934), Neuron, 2014

Mathis and Mathis [Deep learning tools for the measurement of animal behavior in neuroscience](https://www.sciencedirect.com/science/article/abs/pii/S0959438819301151) Current Opinion in Neurobiology 2020

### Day 2

Mathis, Schneider, Lauer, Mathis [A Primer on Motion Capture with Deep Learning: Principles, Pitfalls, and Perspectives](https://www.sciencedirect.com/science/article/pii/S0896627320307170) Neuron 2020

Mathis et al, Nature Neuroscience 2018 or free link: rdcu.be/4Rep

Nath*, Mathis* et al, Nature Protocols 2019 or free link: https://rdcu.be/bHpHN

### Day 3

Kane et al, eLife 2020

Lauer et al. Nature Methods 2022

### Day 4

Wiltschko et al. [Mapping Sub-Second Structure in Mouse Behavior](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4708087/), Neuron 2015


Overview talk, if you want to prepare as the lectures for Tue - Wed are not available yet:

[Recent talk by AM at the CV4ecology Summer School at CalTech](https://www.youtube.com/watch?v=jfIb2qfAkQU)
