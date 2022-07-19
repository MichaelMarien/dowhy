Contributing code
==================================================

Local setup
----------------------------------
To contribute code, basic knowledge of git is required, if you are unfamiliar
with the git workflow, checkout `GitHub's tutorial <https://docs.github.com/en/get-started/quickstart/hello-world>`_.
The following steps allow you to contribute code to DoWhy.

1. Fork the `dowhy main repository <https://github.com/py-why/dowhy>`_
2. Clone this repository to your local machine using

.. code:: shell

   git clone https://github.com/<YOUR_GITHUB_USERNAME>/dowhy

3. (optional) create a virtual environment using python venv or conda

.. code:: shell

   git clone https://github.com/<YOUR_GITHUB_USERNAME>/dowhy

4. For interactive development, its best to install dowhy from source.
This way, you can immediately test your changes to the codebase.

.. code:: shell

   cd dowhy
   pip install --upgrade pip
   pip install -r requirements.txt
   pip install -e .

4. Install additional requirements for development purposes

.. code:: shell

   pip install -r requirements-test.txt

6. (optional) add the dowhy master as an upstream remote to keep your
fork up-to-date with DoWhy's master branch.

.. code:: shell

   git remote add upstream http://www.github.com/py-why/dowhy

You are now ready to make changes to the code base locally.

Pull request checklist
----------------------------------

1. Execute the flake8 linter for breaking warnings and fix all reported problems.

.. code:: shell

  flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics

2. Add tests for your new code and execute the unittests to make sure
you did not introduce any breaking changes or bugs.

.. code:: shell

  pytest -v -m "not advanced"

The full test suite of DoWhy takes quite long. Tto speed up development cycles,
you can restrict the tests executed as in the following example.

.. code:: shell

  pytest -v tests/causal_estimators

3. Once your code is finished and it passes both flake8 and pytest checks successfully,
commit your changes. Make sure to add an informative commit message and to sign off your
commits (DCO):

.. code:: shell

  git commit --signoff -m "informative commit message"
