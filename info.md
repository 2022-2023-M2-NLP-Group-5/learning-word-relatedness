
```shell
─user at s-m2tal in ⌁/projlogiciel/learning-word-relatedness (group5 …2)

+ fdfind -e py -e sh
classifier.py
info.sh
models_builder.py
peak_detection.py
search/__init__.py
search/max_entities_heap.py
search/qe_multiple_entities.py
search/qe_single_entity.py
search/temporal_search.py
utils.py
word2vec_model.py
word2vec_model_alltime.py


+ fdfind -e tsv
data/binary_relations.tsv
data/relations.tsv


+ rg -i nyt -g '!data/*'
word2vec_model_alltime.py
16:        text_files = filter(lambda f: f.endswith('.txt') and re.match(r'nyt-(\d{4}).*$', f),
27:        self.MODEL_PATH = os.path.join(dir_path, 'word2vec-nyt-9999.model')

word2vec_model.py
34:        corpus_filename_str = 'nyt-%i.txt'
36:        self.MODEL_PATH = os.path.join(dir_path, 'word2vec-nyt-%i.model' % year)

models_builder.py
43:                # m = re.match(r'nyt-(\d{4})\.txt$', f)

search/temporal_search.py
30:        self.solr = pysolr.Solr('http://localhost:8983/solr/nyt')
59:        expands a given query using the temporal model, searches NYT and returns a list of articles
94:        expands a given query using the temporal model, searches NYT and returns a list of articles

info.sh
11:rg -i 'nyt' -g !'data/*'


+ rg -g '!*.svg' http
search/temporal_search.py
30:        self.solr = pysolr.Solr('http://localhost:8983/solr/nyt')

info.sh
13:rg -g !'*.svg' 'http'

README.md
9:>https://arxiv.org/abs/1707.08081


+ rg 'word2vec.+\.model'
word2vec_model_alltime.py
27:        self.MODEL_PATH = os.path.join(dir_path, 'word2vec-nyt-9999.model')

word2vec_model.py
36:        self.MODEL_PATH = os.path.join(dir_path, 'word2vec-nyt-%i.model' % year)

info.sh
15:rg 'word2vec.+\.model'


+ rg word2vec.+model
word2vec_model_alltime.py
27:        self.MODEL_PATH = os.path.join(dir_path, 'word2vec-nyt-9999.model')
30:            logging.info('Creating a word2vec model for all time')
39:            logging.info('Loading existing word2vec model')

word2vec_model.py
36:        self.MODEL_PATH = os.path.join(dir_path, 'word2vec-nyt-%i.model' % year)
39:            logging.info('Creating a word2vec model for %i' % year)
45:            logging.info('Loading existing word2vec model')

models_builder.py
9:from word2vec_model import Word2VecModel
56:        # build a word2vec model out of each model file in the 'data' folder
71:        # build a word2vec model out of each model file in the 'data' folder

search/qe_single_entity.py
55:        return tuples (term, score) of the k closest terms from the word2vec model of that time period
74:        find top 10 closest terms from the word2vec model of that time period
97:        find top 10 closest terms from the word2vec model of that time period

info.sh
15:rg 'word2vec.+\.model'
17:rg 'word2vec.+model'

code2flow.reporoot.svg
90:<text text-anchor="middle" x="2200.25" y="-1505.8" font-family="Times,serif" font-size="14.00">File: word2vec_model</text>
105:<text text-anchor="middle" x="1023.25" y="-1082.8" font-family="Times,serif" font-size="14.00">File: word2vec_model_alltime</text>

README.md
13: 1. code for creating word embeddings using word2vec, either from a single corpus (`word2vec_model_alltime.py`), or from a temporal corpus (`models_builder.py`)

utils.py
66:    :param year_to_model: a dictionary, mapping year to word2vec model
225:    :param year_to_model: a mapping between each year and its word2vec model


+ rg binary_relations -g '!*.svg'
info.sh
19:rg 'binary_relations' -g !'*.svg'

utils.py
59:def read_binary_relations_to_features(relations_file_name, year_to_model=None, global_model=None,
76:        logging.critical('utils.read_binary_relations_to_features got both global_model and year_to_model!')
79:        logging.critical("utils.read_binary_relations_to_features didn't receive a model!")
209:def filter_relations_with_binary_relations(relations, binary_relations):
216:        if any((bin_rel[0] == entity1 and bin_rel[1] == entity2) for bin_rel in binary_relations):

```
