

- Working with a [[s.l.python.libs.sqlite3]] database using sql alchemy

```python
from sqlalchemy import create_engine
from sqlalchemy import Column

from sqlalchemy import String
from sqlalchemy import DateTime
from sqlalchemy import Integer

from sqlalchemy import select
from sqlalchemy import Table
from sqlalchemy import Identity
from sqlalchemy import MetaData

from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

import pandas as pd
from sqlalchemy.sql.elements import Null

engine = create_engine("sqlite:///test_db.db")
session = sessionmaker(bind=engine)()
# con = engine.connect()

Base = declarative_base()

class Log(Base):

  __tablename__="Log"

  Log_ID = Column(Integer, primary_key=True)
  Email_ID = Column(Integer)
  Ticket_ID = Column(Integer)
  Work_Item_ID = Column(Integer)

  def __init__(self, Log_ID, Email_ID, Ticket_ID, Work_Item_ID):
	  self.Log_ID = Log_ID
	  self.Email_ID = Email_ID
	  self.Ticket_ID = Ticket_ID
	  self.Work_Item_ID = Work_Item_ID

logentry = Log(1, Null, Null, Null)


session.add(logentry)
session.commit()
```
