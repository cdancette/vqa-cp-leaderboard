
VQA-CP  Leaderboard
===================

A collections of papers about VQA-CP datasets and their results


VQA-CP v2
***********


+--------------+---------------+-----------+------------+------------+------------+------------+
|     Name     |  Conference   |    All    |   Yes/No   |  Numbers   |   Other    | Validation |
+==============+===============+===========+============+============+============+============+
| GradSup_     | ECCV 2020     | 46.8      | 64.5       | 15.3       | 45.9       | **Valset** |
+--------------+---------------+-----------+------------+------------+------------+------------+
| VGQE_        | ECCV 2020     | 50.11     | 66.35      | 27.08      | 46.77      | No valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+
| CSS_         | CVPR 2020     | **58.95** | **84.37**  | **49.42**  | **48.21**  | No valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+
| Unshuffling_ | Preprint 2020 | 42.39     | 47.72      | 14.43      | 47.24      | **Valset** |
+--------------+---------------+-----------+------------+------------+------------+------------+
| LMH_         | EMNLP 2019    | 52.05     | 69.81 [1]_ | 44.46 [1]_ | 45.54 [1]_ | No valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+
| RUBi_        | NeurIPS 2019  | 47.11     | 68.65      | 20.28      | 43.18      | No valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+
| HINT_ [2]_   | ICCV 2019     | 46.73     | 67.27      | 10.61      | 45.88      | No valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+
| ActSeek_     | CVPR 2019     | 46.00     | 58.24      | 29.49      | 44.33      | **ValSet** |
+--------------+---------------+-----------+------------+------------+------------+------------+
| AdvReg_      | NeurIPS 2018  | 41.17     | 65.49      | 15.48      | 35.48      | No Valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+
| GVQA_        | CVPR 2018     | 31.30     | 57.99      | 13.68      | 22.14      | No valset  |
+--------------+---------------+-----------+------------+------------+------------+------------+

.. [1] Retrained by CSS_
.. [2] Using additional information

VQA-CP v1
*********

Papers
******

.. .. |br| raw:: html

..    <br />


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
_`Unshuffling`
    |  Unshuffling Data for Improved Generalization -  **Preprint 2020** 
    | Damien Teney, Ehsan Abbasnejad, Anton van den Hengel
    | https://arxiv.org/abs/2002.11894

        .. raw:: html

            <details><summary>Summary</summary>

            Inspired by Invariant Risk Minimization (Arjovskyet al.).
            They make use of two training sets with different
            biases to learn a more robust classifier (that will perform
            better on OOD data). 

            </details>

_`LMH`
    | Don’t Take the Easy Way Out: Ensemble Based Methods for Avoiding Known Dataset Biases -  **EMNLP 2019** 
    | Christopher Clark, Mark Yatskar, Luke Zettlemoyer
    | https://arxiv.org/abs/1909.03683
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
  
_`HINT`
    | Taking a HINT: Leveraging Explanations to Make Vision and Language Models More Grounded
    | Ramprasaath R. Selvaraju, Stefan Lee, Yilin Shen, Hongxia Jin, Shalini Ghosh, Larry Heck, Dhruv Batra, Devi Parikh
    | https://arxiv.org/abs/1902.03751
_`ActSeek`
    | Actively Seeking and Learning from Live Data -  **CVPR 2019** 
    | Damien Teney, Anton van den Hengel
    | https://arxiv.org/abs/1904.02865
_`AdvReg`
    | Overcoming Language Priors in Visual Question Answering with Adversarial Regularization -  **NeurIPS 2018** 
    | Sainandan Ramakrishnan, Aishwarya Agrawal, Stefan Lee
    | https://papers.nips.cc/paper/7427-overcoming-language-priors-in-visual-question-answering-with-adversarial-regularization.pdf
_`GVQA`
    | Don’t Just Assume; Look and Answer: Overcoming Priors for Visual Question Answering -  **CVPR 2018** 
    | Aishwarya Agrawal, Dhruv Batra, Devi Parikh, Aniruddha Kembhavi
    | https://arxiv.org/abs/1712.00377

