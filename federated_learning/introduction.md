## Links

[Presentation material](https://ecaad164-c957-4008-a451-5e1098ff8953.filesusr.com/ugd/68a50d_a3d074241b3a4342be2fef2413ee61c7.pdf)
[Colab notebook - part 1](https://colab.research.google.com/drive/1_uemRwNuok1wop6wP2Aiokn0KQgcwfr1?usp=sharing)
[Colab notebook - part 2](https://colab.research.google.com/drive/1PiUee4n8T7pIhDV5zDEqhsK5jXvDYHpO?usp=sharing)
[Colab notebook - part 3](https://colab.research.google.com/drive/1kIbrUtNH_WIPQX5vLyzRjs5CTgKA2CMT?usp=sharing)
[Colab notebook - part 4](https://colab.research.google.com/drive/10wEN9eqdE9Z7CtvhRFgsL3gAzunZGlee?usp=sharing)

# Introduction

Standard machine learning approaches require to have a centralizaed dataset in order to train a model. In certain scenarios like in the biomedical field, this is not straightforward due to several reasons like:

* Privacy concerns:
  * General Data Protection Regulation (GDPR): [General Data Protection Regulation (GDPR) – Official Legal Text](https://gdpr-info.eu/)
  * Californian Consumer Privacy Act (CCPA): [California Consumer Privacy Act (CCPA) | State of California - Department of Justice - Office of the Attorney General](https://oag.ca.gov/privacy/ccpa)
* Ethical committee approval
* Transferring data to a centralized location

This slows down research in healthcare and limits the generalization of certain models.

## Federated Learning

Federated learning (FL) is a machine learning procedure whose goal is to train a model without having data centralized. The goal of FL is to train higher quality models by having access to more data than centralized approaches, as well as to keep data securely decentralized. 

### Infrastructure of a federated learning setting in healthcare

A common scenario of federated learning in healthcare is shown as follows:

![](./fl-graph.png)

Hospitals (a.k.a. clients) across several geographical locations hold data of interest for a researcher. These data can be "made available" for local training but, only the model is authorized to be shared with a third thrusted party (e.g. research center). Once all the models are gathered, different techniques are proposed for **aggregating** them as a single global model. Then, the **Aggregated model** can be used as purposed (e.g. training a neural network for segmentation).

### Theoretical background

One of the critical points in FL is knowing how to aggregate the models submitted by the clients. The main problem relies on finding the best set of **parameters** that define your model in function of the submissions made by the clients.

In a canonical form:

$$
\min_w F(w) ,\quad \textrm{where} F(w):=\sum_{k=1}^{m} p_k F_k(w)
$$

Where $m$ is the total number of clients, $p_k>=0$, and $\sum_k p_k=1$ , and $F_k$ is the local objective function for the $k$-th client. The impact (contribution) of each client to the aggregation of the global model is given by $p_k$.

One of the first proposed methodologies in FL for model aggregation was **Federated Averaging `FedAVG`** by (MacMahan _et_ al, 2016), the idea behind it was to define the contribution of each client as $p_k=\frac{n_k}{n}$ where $n_k$ is the number of datapoints in the client $k$ and $n$ is the total number of observations studied.

### Challenges in federated learning

The main challenges in FL are associated to:

- **Communication efficiency:** number of iterations between clients and central location to train an optimal model.

- **Data heterogeneity:** how to build generalized models with heterogeneous data?

- **Security:** adversarial attacks and data leakage.

---

## References

1. **Konečný, J., McMahan, et al. (2016).** *Federated learning: Strategies for improving communication efficiency*. arXiv preprint arXiv:1610.05492.

2. **Li, T., Sahu, et al. (2018).** *Federated optimization in heterogeneous networks.* arXiv preprint arXiv:1812.06127.

3. **Li, T., Sahu, A. K., Talwalkar, A., & Smith, V. (2020).** *Federated learning: Challenges, methods, and future directions*. IEEE Signal Processing Magazine, 37(3), 50-60.



