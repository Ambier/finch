<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/tensorflow_nlp.png" height='100'>

---
#### Contents
* [Word Embedding（词向量）](https://github.com/zhedongzheng/finch#word-embedding%E8%AF%8D%E5%90%91%E9%87%8F)
* [Text Classification（文本分类）](https://github.com/zhedongzheng/finch#text-classification%E6%96%87%E6%9C%AC%E5%88%86%E7%B1%BB)
* [Text Generation（文本生成）](https://github.com/zhedongzheng/finch#text-generation%E6%96%87%E6%9C%AC%E7%94%9F%E6%88%90)
* [Text Matching（文本匹配）](https://github.com/zhedongzheng/finch/blob/master/README.md#text-matching%E6%96%87%E6%9C%AC%E5%8C%B9%E9%85%8D)
* [Sequence Labelling（序列标记）](https://github.com/zhedongzheng/finch#sequence-labelling%E5%BA%8F%E5%88%97%E6%A0%87%E8%AE%B0)
* [Sequence to Sequence（序列到序列）](https://github.com/zhedongzheng/finch#sequence-to-sequence%E5%BA%8F%E5%88%97%E5%88%B0%E5%BA%8F%E5%88%97)
* [Question Answering（问题回答）](https://github.com/zhedongzheng/finch/blob/master/README.md#question-answering%E9%97%AE%E9%A2%98%E5%9B%9E%E7%AD%94)
* [Knowledge Graph（知识图谱）](https://github.com/zhedongzheng/finch#knowledge-graph%E7%9F%A5%E8%AF%86%E5%9B%BE%E8%B0%B1)

---
#### Installation 
* Python 3 and [Jupyter Notebook](http://jupyter.org/) are required

    ```
    (CPU User) $ pip3 install tensorflow==1.6.0 sklearn scipy tqdm
    
    (GPU User) $ pip3 install tensorflow-gpu==1.6.0 sklearn scipy tqdm
    ```
---

* [feeding](https://www.tensorflow.org/api_guides/python/reading_data#Feeding) is the most common and flexible interface, but not efficient for industry use

* Starting to move existing code into new interfaces [tf.data.Dataset](https://www.tensorflow.org/api_docs/python/tf/data/Dataset) and [tf.estimator.Estimator](https://www.tensorflow.org/api_docs/python/tf/estimator/Estimator)
---

#### Word Embedding（词向量）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/decoration_6.png" height='100'>

* [Interface: feeding](https://www.tensorflow.org/api_guides/python/reading_data#Feeding)

    * Skip-Gram &nbsp; &nbsp; [Model](https://github.com/zhedongzheng/finch/blob/master/nlp-models/tensorflow/word2vec_skipgram.py) &nbsp; &nbsp; [PTB Test](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/word2vec_skipgram_test.ipynb)

    * CBOW &nbsp; &nbsp; [Model](https://github.com/zhedongzheng/finch/blob/master/nlp-models/tensorflow/word2vec_cbow.py) &nbsp; &nbsp; [PTB Test](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/word2vec_cbow_test.ipynb)

#### Text Classification（文本分类）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/decoration_2.png" height='100'>

* [Interface: tf.estimator.Estimator](https://www.tensorflow.org/api_docs/python/tf/estimator)

    * [IMDB Movie Reviews Sentiment](http://ai.stanford.edu/~amaas/data/sentiment/)

        *  [CNN](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-estimator/concat_conv_1d_text_clf_imdb_test.ipynb)

        *  [Bi-RNN](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-estimator/rnn_text_clf_imdb_test.ipynb)

        *  [Attention (no RNN / CNN)](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-estimator/only_attn_text_clf_imdb_test.ipynb)

        *  [TF-IDF + LR](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-estimator/tfidf_imdb_test.ipynb)

#### Text Generation（文本生成）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/decoration_5.png" height='100'>

* [Interface: tf.data.Dataset](https://www.tensorflow.org/api_docs/python/tf/data)

    * Writing《Anna Karenina》
    
        * [RNN Language Model](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-data-api/char_rnn_beam_test.ipynb)
    
        *  [Attention Language Model (no RNN / CNN)](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-data-api/self_attn_lm_test.ipynb)

* [Interface: feeding](https://www.tensorflow.org/api_guides/python/reading_data#Feeding)

    * Character Aware Language Model &nbsp; &nbsp; [Model](https://github.com/zhedongzheng/finch/blob/master/nlp-models/tensorflow/cnn_rnn_text_gen.py) &nbsp; &nbsp; [PTB Test](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/cnn_rnn_text_gen_test.ipynb) &nbsp; &nbsp;

    * [IMDB Movie Reviews](http://ai.stanford.edu/~amaas/data/sentiment/)

        * [VAE](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/vae)
        
        * [Controllable VAE](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/toward-control)

#### Text Matching（文本匹配）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/decoration_10.jpeg" height='200'>

* [Interface: tf.estimator.Estimator](https://www.tensorflow.org/api_docs/python/tf/estimator)

    * [Movielens](https://grouplens.org/datasets/movielens/)

        * [User-Item Matching](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/movielens)

#### Sequence Labelling（序列标记）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/decoration_4.jpg" height='100'>

* [Interface: tf.data.Dataset](https://www.tensorflow.org/api_docs/python/tf/data)

    * [POS Tagging](https://www.clips.uantwerpen.be/conll2000/chunking/)

        * [Bi-RNN + CRF](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-data-api/pos_birnn_crf_test.ipynb)

        * [CNN + CRF](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-data-api/cnn_seq_label_pos_test.ipynb)

    * [Chinese Segmentation](http://sighan.cs.uchicago.edu/bakeoff2005/)

        * [Bi-RNN + CRF](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-data-api/chseg_birnn_crf_test.ipynb)

        * [CNN + CRF](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/tf-data-api/cnn_seq_label_chseg_test.ipynb)

#### Sequence to Sequence（序列到序列）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/decoration_1.png" height='100'>

* [Interface: tf.estimator.Estimator](https://www.tensorflow.org/api_docs/python/tf/estimator)

    * Learning to Sort

        * [Attention Is All You Need](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/attn_is_all_u_need)

* [Interface: feeding](https://www.tensorflow.org/api_guides/python/reading_data#Feeding)

    * Learning to Sort

        * Seq2Seq + Bi-Encoder + Attention + Beam-Search &nbsp; &nbsp; [Model](https://github.com/zhedongzheng/finch/blob/master/nlp-models/tensorflow/seq2seq_ultimate.py) &nbsp; &nbsp; [Test](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/seq2seq_ultimate_test.ipynb) 

        * Pointer Network &nbsp; &nbsp; [Model](https://github.com/zhedongzheng/finch/blob/master/nlp-models/tensorflow/pointer_net.py) &nbsp; &nbsp; [Test](https://nbviewer.jupyter.org/github/zhedongzheng/finch/blob/master/nlp-models/tensorflow/pointer_net_test.ipynb)

    * Speech Recognition

        * [CTC](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/asr)

#### Question Answering（问题回答）
<img src="https://github.com/zhedongzheng/finch/blob/master/nlp-models/assets/dmn-details.png" height='100'>

* [Interface: feeding](https://www.tensorflow.org/api_guides/python/reading_data#Feeding)

    * [Facebook bAbI](https://research.fb.com/downloads/babi/)

        * [End-To-End Memory Network](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/end2end_mn) 

        * [Dynamic Memory Network](https://github.com/zhedongzheng/finch/tree/master/nlp-models/tensorflow/dmn) 

#### Knowledge Graph（知识图谱）
* [Course Notes](https://github.com/zhedongzheng/finch/blob/master/nlp-models/kg/notes.md)
