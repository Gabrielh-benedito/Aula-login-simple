# Iniciando o alembic
no terminal:
```bash
python -m alembic init migrations
```

# Apagar o valor da linha 89 - no arquivo alembic.init
deixe assim :
sqlalchemy.url = 

# Edite o arquivo migration/env.py:

from dotenv import load_dotenv
import os
import database
from database import Base

config.set_main_option("sqlalchemy.url ", os.getenv("DATABASE_URL"))

target_metadata = Base.metadata

# Gere a migration com autogenerate

``` bash
python -m alembic revision --autogenerate -m "Cria tabela usuario"
```

# Aplicar a migration

``` bash
python -m alembic upgrade head
```