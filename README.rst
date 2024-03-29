
VQA-CP  Leaderboard
===================

A collections of papers about the VQA-CP dataset and a benchmark / leaderboard of their results.
VQA-CP_ is an out-of-distribution dataset for Visual Question Answering,
which is designed to penalize models that rely on question biases to give an answer.
You can download VQA-CP annotations here : https://computing.ece.vt.edu/~aish/vqacp/

Notes:

- All reported papers do not use the same baseline architectures, 
  so the scores might not be directly comparable. This leaderboard 
  is only made as a reference of all bias-reduction methods that 
  were tested on VQA-CP.

- We mention the presence or absence of a validation set, because 
  for out-of-distribution datasets, it is very important to find hyperparameters 
  and do early-stopping on a validation set that has the same distribution as 
  the training set. Otherwise, there is a risk of overfitting the testing set 
  and its biases, which defeats the point of the VQA-CP dataset. This is why we 
  **highly recommand**  for future work that they build a  **validation set**  
  from a part of training set.


You can read an overview of some of those bias-reduction methods here: https://cdancette.fr/2020/11/21/overview-bias-reductions-vqa/


VQA-CP v2
***********

In bold are highlighted best results on architectures without pre-training.

+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| Name            | Base Arch.           | Conference              | All       | Yes/No     | Numbers    | Other      | Validation |
+=================+======================+=========================+===========+============+============+============+============+
| AttReg_ [2]_    | LMH_                 | Preprint                | 59.92     | 87.28      | 52.39      | 47.65      |            |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| GGE-DQ_         | UpDown               | ICCV 2021               | 57.32     | 87.04      | 27.75      | 49.59      |            |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| AdaVQA_         | UpDown               | IJCAI 2021              | 54.67     | 72.47      | 53.81      | 45.58      | No Valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| DecompLR_       | UpDown               | AAAI 2020               | 48.87     | 70.99      | 18.72      | 45.57      | No Valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| MUTANT_         | LXMERT               | EMNLP 2020              | 69.52     | 93.15      | 67.17      | 57.78      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| MUTANT_         | UpDown               | EMNLP 2020              | **61.72** | **88.90**  | **49.68**  | **50.78**  | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| CL_             | UpDown + LMH_ + CSS_ | EMNLP 2020              | 59.18     | 86.99      | 49.89      | 47.16      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| RMFE_           | UpDown + LMH_        | NeurIPS 2020            | 54.55     | 74.03      | 49.16      | 45.82      | No Valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| RandImg_        | UpDown               | NeurIPS 2020            | 55.37     | 83.89      | 41.60      | 44.20      | Valset     |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| Loss-Rescaling_ | UpDown + LMH_        | Preprint 2020           | 53.26     | 72.82      | 48.00      | 44.46      |            |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| ESR_            | UpDown               | ACL 2020                | 48.9      | 69.8       | 11.3       | 47.8       |            |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| GradSup_        | Unshuffling_         | ECCV 2020               | 46.8      | 64.5       | 15.3       | 45.9       | **Valset** |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| VGQE_           | S-MRL                | ECCV 2020               | 50.11     | 66.35      | 27.08      | 46.77      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| CSS_            | UpDown + LMH_        | CVPR 2020               | 58.95     | 84.37      | 49.42      | 48.21      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| Semantic_       | UpDn + RUBi_         | Preprint 2020           | 47.5      |            |            |            |            |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| Unshuffling_    | UpDown               | Preprint 2020           | 42.39     | 47.72      | 14.43      | 47.24      | **Valset** |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| CF-VQA_         | UpDown + LMH_        | Preprint 2020           | 57.18     | 80.18      | 45.62      | 48.31      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| LMH_            | UpDown               | EMNLP 2019              | 52.05     | 69.81 [1]_ | 44.46 [1]_ | 45.54 [1]_ | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| RUBi_           | S-MRL [3]_           | NeurIPS 2019            | 47.11     | 68.65      | 20.28      | 43.18      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| SCR_ [2]_       | UpDown               | NeurIPS 2019            | 49.45     | 72.36      | 10.93      | 48.02      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| NSM_            |                      | NeurIPS 2019            | 45.80     |            |            |            |            |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| HINT_ [2]_      | UpDown               | ICCV 2019               | 46.73     | 67.27      | 10.61      | 45.88      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| ActSeek_        | UpDown               | CVPR 2019               | 46.00     | 58.24      | 29.49      | 44.33      | **ValSet** |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| GRL_            | UpDown               | NAACL-HLT 2019 Workshop | 42.33     | 59.74      | 14.78      | 40.76      | **Valset** |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| AdvReg_         | UpDown               | NeurIPS 2018            | 41.17     | 65.49      | 15.48      | 35.48      | No Valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+
| GVQA_           |                      | CVPR 2018               | 31.30     | 57.99      | 13.68      | 22.14      | No valset  |
+-----------------+----------------------+-------------------------+-----------+------------+------------+------------+------------+

.. [1] Retrained by CSS_
.. [2] Using additional information
.. [3] S-MRL stands for Simplified-MUREL. The architecture was proposed in RUBi_.

.. VQA-CP v1
.. *********

Papers
******

.. .. |br| raw:: html

..    <br />

_`GGE-DQ`
    | Greedy Gradient Ensemble for Robust Visual Question Answering
    | Xinzhe Han, Shuhui Wang, Chi Su, Qingming Huang, Qi Tian
    | https://arxiv.org/pdf/2107.12651.pdf
_`DecompLR`
    | Overcoming language priors in vqa via decomposed linguistic representations
    | Chenchen Jing, Yuwei Wu, Xiaoxun Zhang, Yunde Jia, Qi Wu
    | https://ojs.aaai.org/index.php/AAAI/article/view/6776
_`AdaVQA`
    | AdaVQA: Overcoming Language Priors with Adapted Margin Cosine Loss
    | Yangyang Guo, Liqiang Nie, Zhiyong Cheng, Feng Ji, Ji Zhang, Alberto Del Bimbo
    | https://arxiv.org/pdf/2105.01993.pdf

_`MUTANT`
    | MUTANT: A Training Paradigm for Out-of-Distribution Generalization in Visual Question Answering -  **EMNLP 2020** 
    | Tejas Gokhale, Pratyay Banerjee, Chitta Baral, Yezhou Yang
    | https://www.aclweb.org/anthology/2020.emnlp-main.63/
    | code: https://github.com/tejas-gokhale/vqa_mutant
_`CL`
    | Learning to Contrast the Counterfactual Samples for Robust Visual Question Answering   -  **EMNLP 2020** 
    | Zujie Liang, Weitao Jiang, Haifeng Hu, Jiaying Zhu                                                       
    | https://www.aclweb.org/anthology/2020.emnlp-main.265.pdf                                                 
_`RMFE`
    | Removing Bias in Multi-modal Classifiers: Regularization by Maximizing Functional Entropies -  **NeurIPS 2020** 
    | Itai Gat, Idan Schwartz, Alexander Schwing, Tamir Hazan                                                         
    | https://proceedings.neurips.cc/paper/2020/hash/20d749bc05f47d2bd3026ce457dcfd8e-Abstract.html   
    | code: https://github.com/itaigat/removing-bias-in-multi-modal-classifiers             
_`RandImg`
    | On the Value of Out-of-Distribution Testing:An Example of Goodhart’s Law
    | Damien Teney, Kushal Kafle, Robik Shrestha, Ehsan Abbasnejad, Christopher Kanan, Anton van den Hengel
    | https://arxiv.org/abs/2005.09241
_`Loss-Rescaling`
    | Loss-rescaling VQA: Revisiting Language Prior Problem from a Class-imbalance View - **Preprint 2020** 
    | Yangyang Guo, Liqiang Nie, Zhiyong Cheng, Qi Tian                                                     
    | https://arxiv.org/abs/2010.16010                                                                      
_`ESR` (Embarrassingly Simple Regularizer)
    | A Negative Case Analysis of Visual Grounding Methods for VQA - **ACL 2020**
    | Robik Shrestha, Kushal Kafle, Christopher Kanan
    | https://www.aclweb.org/anthology/2020.acl-main.727.pdf
_`GradSup`
    | Learning what makes a difference from counterfactual examples and gradient supervision -  **ECCV 2020** 
    | Damien Teney, Ehsan Abbasnedjad, Anton van den Hengel                                                   
    | https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123550579.pdf                                  
_`VGQE`
    | Reducing Language Biases in Visual Question Answering with Visually-Grounded Question Encoder  -  **ECCV 2020** 
    | Gouthaman KV, Anurag Mittal                                                                                     
    | https://arxiv.org/abs/2007.06198                                                                                
_`CSS`
    | Counterfactual Samples Synthesizing for Robust Visual Question Answering -  **CVPR 2020** 
    | Long Chen, Xin Yan, Jun Xiao, Hanwang Zhang, Shiliang Pu, Yueting Zhuang                  
    | https://arxiv.org/abs/2003.06576    
    | code: https://github.com/yanxinzju/CSS-VQA                                                      
_`Semantic`
    | Estimating semantic structure for the VQA answer space  -  **Preprint 2020** 
    | Corentin Kervadec, Grigory Antipov, Moez Baccouche, Christian Wolf           
    | https://arxiv.org/abs/2006.05726                                             
_`Unshuffling`
    | Unshuffling Data for Improved Generalization -  **Preprint 2020** 
    | Damien Teney, Ehsan Abbasnejad, Anton van den Hengel              
    | https://arxiv.org/abs/2002.11894                         

        .. raw:: html

            <details><summary>Summary</summary>

            Inspired by Invariant Risk Minimization (Arjovskyet al.).
            They make use of two training sets with different
            biases to learn a more robust classifier (that will perform
            better on OOD data). 

            </details>

_`CF-VQA`
    | Counterfactual VQA: A Cause-Effect Look at Language Bias  -  **Preprint 2020** 
    | Yulei Niu, Kaihua Tang, Hanwang Zhang, Zhiwu Lu, Xian-Sheng Hua, Ji-Rong Wen   
    | https://arxiv.org/abs/2006.04315v2                                             

        .. raw:: html

            <details><summary>Summary</summary>

        They formalize the ensembling framwork from RUBi_ and LMH_ using
        the causality framework.

        .. raw:: html

            </details>

_`LMH`
    | Don’t Take the Easy Way Out: Ensemble Based Methods for Avoiding Known Dataset Biases -  **EMNLP 2019** 
    | Christopher Clark, Mark Yatskar, Luke Zettlemoyer                                                       
    | https://arxiv.org/abs/1909.03683     
    | code: https://github.com/chrisc36/bottom-up-attention-vqa                                                                   
_`RUBi`
    | RUBi: Reducing Unimodal Biases in Visual Question Answering  -  **NeurIPS 2019** 
    | Remi Cadene, Corentin Dancette, Hedi Ben-younes, Matthieu Cord, Devi Parikh      
    | https://arxiv.org/abs/1906.10169                                                 

        .. raw:: html
            
            <details><summary>Summary</summary>        
                <p>During training : Ensembling with a question-only model that will learn the biases, and let the main VQA model learn
                useful behaviours.</p>

                <p>During testing: We remove the question-only model, and keep only the VQA model.</p>
            
            </details>

    | code: https://github.com/cdancette/rubi.bootstrap.pytorch

_`NSM`
    | Learning by Abstraction: The Neural State Machine
    | Drew A. Hudson, Christopher D. Manning
    | https://arxiv.org/abs/1907.03950



_`SCR` 
    | Self-Critical Reasoning for Robust Visual Question Answering -  **NeurIPS 2019** 
    | Jialin Wu, Raymond J. Mooney                                                     
    | https://arxiv.org/abs/1905.09998    
    | code: https://github.com/jialinwu17/self_critical_vqa
_`HINT`
    | Taking a HINT: Leveraging Explanations to Make Vision and Language Models More Grounded -  **ICCV 2019**           
    | Ramprasaath R. Selvaraju, Stefan Lee, Yilin Shen, Hongxia Jin, Shalini Ghosh, Larry Heck, Dhruv Batra, Devi Parikh 
    | https://arxiv.org/abs/1902.03751                                                                                   
_`ActSeek`
    | Actively Seeking and Learning from Live Data -  **CVPR 2019** 
    | Damien Teney, Anton van den Hengel                            
    | https://arxiv.org/abs/1904.02865                              
_`GRL`
    | Adversarial Regularization for Visual Question Answering:Strengths, Shortcomings, and Side Effects -  **NAACL HLT - Workshop on Shortcomings in Vision and Language (SiVL) **
    | Gabriel Grand, Yonatan Belinkov
    | https://arxiv.org/pdf/1906.08430.pdf
    | code: https://github.com/gabegrand/adversarial-vqa
_`AdvReg`
    | Overcoming Language Priors in Visual Question Answering with Adversarial Regularization -  **NeurIPS 2018**                   
    | Sainandan Ramakrishnan, Aishwarya Agrawal, Stefan Lee                                                                         
    | https://papers.nips.cc/paper/7427-overcoming-language-priors-in-visual-question-answering-with-adversarial-regularization.pdf 
    | code: 
_`GVQA`
    | Don’t Just Assume; Look and Answer: Overcoming Priors for Visual Question Answering -  **CVPR 2018** 
    | Aishwarya Agrawal, Dhruv Batra, Devi Parikh, Aniruddha Kembhavi                                      
    | https://arxiv.org/abs/1712.00377
    | code: https://github.com/AishwaryaAgrawal/GVQA                                                              



.. _VQA-CP: https://arxiv.org/abs/1712.00377
