## To build pip package and upload to the: "https://pypi.org/"

### Create a setup file in package root directory:
```
from setuptools import setup
setup(
  name = 'todo_webapp',         #* Your package will have this name
  packages = ['todo_webapp'],   #* Name the package again
  version = '1.0.3',         #* To be increased every time your change your library
  include_package_data=True,
  license='MIT',             # Type of license. More here: https://help.github.com/articles/licensing-a-repository
  description = 'This package can be used to run both desktop to-do app (python3 todo-list-GUI.py and todo-list-CLI.py ) '
                'and web based to-do app (streamlit run main.py) to save and manage daily To-Do tasks.'
                'Please note: Add "todos.txt" file and an image named add.png in your instaled directory!',    # Short description of your library
  author = 'Abdul Rahman, Vakili',                   # Your name
  author_email = 'vakili.hu.it@gamil.com',  # Your email
  url = 'https://de.linkedin.com/in/abdul-rahman-vakili-052172120',              # Homepage of your library (e.g. github or your website)
  keywords = ['to-do', 'task'],   # Keywords users can search on pypi.org
  install_requires=['PySimpleGUI','streamlit'],                 # Other 3rd-party libs that pip needs to install
  classifiers=[
    'Development Status :: 3 - Alpha',          # Chose either "3 - Alpha", "4 - Beta" or "5 - Production/Stable" as the current state of your package
    'Intended Audience :: Developers',          # Who is the audience for your library?
    'Topic :: Software Development :: Build Tools',
    'License :: OSI Approved :: MIT License',   # Type a license again
    'Programming Language :: Python :: 3.8',      # Python versions that your library supports
    'Programming Language :: Python :: 3.9',
    'Programming Language :: Python :: 3.10',
    'Programming Language :: Python :: 3.11',
  ],
)
```

### Add extra files if requred into MANIFEST.in:

```
include add.png
include todos.txt
```

### Build the dist:
``
python3 setup.py sdist
``

### upload with your credential (eg: API Token)
```
twine upload --skip-existing dist/*
```
