# CS 5608 Machin Learning Final Project Code
<div align="center">

# **VAE-based Graph Generation for Multi-View Graph Clustering**

Jianpeng Chen, Hanwen Ju, Nickolas Paraskevopoulos, Rayan Bouhal
</div>

---


# Requirements

- Python >= 3.8
- Pytorch >= 1.11.0
- munkres >= 1.1.4
- scikit-learn >= 1.0.1
- scipy >= 1.8.0


# Datasets

ACM and DBLP are included in `./data/`. The other datasets are public available. 

|     Dataset      | #Clusters | #Nodes |   #Features    |                            Graphs                            |
| :--------------: | :-------: | :----: | :------------: | :----------------------------------------------------------: |
|       ACM        |     3     |  3025  |      1830      |   $\mathcal{G}^1$ co-paper<br />$\mathcal{G}^2$ co-subject   |
|       DBLP       |     4     |  4057  |      334       | $\mathcal{G}^1$ co-author<br />$\mathcal{G}^2$ co-conference<br />$\mathcal{G}^3$ co-term |

Run main.py will train and test the code.

# Training

```python
# Train on ACM dataset
python main.py --dataset acm --train true --model_name vgmgc_acm1.pkl --order 8 --weight_soft 0.9 --min_belief 0.7 --max_belief 0.99 --lam_emd 1 --kl_step 5 --lam_elbo_kl 1 --threshold 0.8 --temperature 5

# Train on DBLP dataset
python main.py --dataset dblp --train true --model_name vgmgc_dblp1.pkl --order 8 --weight_soft 0.1 --min_belief 0.2 --max_belief 0.99 --lam_emd 5 --kl_step 10 --lam_elbo_kl 1 --threshold 0.8 --temperature 1
