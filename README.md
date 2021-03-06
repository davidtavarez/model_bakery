# Model Bakery: Smart fixtures for better tests

*Model Bakery* offers you a smart way to create fixtures for testing in
Django.
With a simple and powerful API you can create many objects with a single
line of code.

Model Bakery is a rename of the legacy [Model Mommy project](https://pypi.org/project/model_mommy/).

[![Test Status](https://travis-ci.com/model-bakers/model_bakery.svg?branch=master)](https://travis-ci.com/model-bakers/model_bakery/)
[![Latest PyPI version](https://img.shields.io/pypi/v/model_bakery.svg)](https://pypi.python.org/pypi/model_bakery/)
[![Documentation Status](https://readthedocs.org/projects/model-bakery/badge/?version=latest)](https://model-bakery.readthedocs.io/en/latest/?badge=latest)

## Install

```bash
pip install model_bakery
```

## Usage and Info

### Basic usage

```python

# models.py

class Customer(models.Model):
    happy = models.BooleanField()
    name = models.CharField(max_length=30)
    age = models.IntegerField()
    bio = models.TextField()
    wanted_games_qtd = models.BigIntegerField()
    birthday = models.DateField()
    last_shopping = models.DateTimeField()

# test_models.py

from django.test import TestCase
from model_bakery import baker
from pprint import pprint

class TestCustomerModel(TestCase):
    def setUp(self):
        self.customer = baker.make('shop.Customer')
        pprint(self.customer.__dict__)

"""
{'_state': <django.db.models.base.ModelState object at 0x1129a3240>,
 'age': 3841,
 'bio': 'vUFzMUMyKzlnTyiCxfgODIhrnkjzgQwHtzIbtnVDKflqevczfnaOACkDNqvCHwvtWdLwoiKrCqfppAlogSLECtMmfleeveyqefkGyTGnpbkVQTtviQVDESpXascHAluGHYEotSypSiHvHzFteKIcUebrzUVigiOacfnGdvijEPrZdSCIIBjuXZMaWLrMXyrsUCdKPLRBRYklRdtZhgtxuASXdhNGhDsrnPHrYRClhrSJSVFojMkUHBvSZhoXoCrTfHsAjenCEHvcLeCecsXwXgWJcnJPSFdOmOpiHRnhSgRF',
 'birthday': datetime.date(2019, 12, 3),
 'happy': True,
 'id': 1,
 'last_shopping': datetime.datetime(2019, 12, 3, 21, 42, 34, 77019),
 'name': 'qiayYnESvqcYLLBzxpFOcGBIfnQEPx',
 'wanted_games_qtd': 6016}
"""

```

Check out [documentation](<http://model-bakery.readthedocs.org/>) for more complete examples. 

## Maintainers

  - [Ana Paula Gomes](https://github.com/anapaulagomes/)
  - [Bernardo Fontes](https://github.com/berinhard/)
  - [Rustem Saiargaliev](https://github.com/amureki/)

## Creator

  - [Vanderson Mota](https://github.com/vandersonmota/)
