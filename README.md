```python
from api_client_core import BaseAPI, endpoint
from api_client_core.types import RestResponse


class UsersAPI(BaseAPI):
    
    @endpoint.get("/users/{username}")
    def get_user(self, username: str) -> RestResponse:
        ...
```

```pycon
>>> client = MyAPIClient()
>>> r = client.Users.get_user("yugokato")
>>> assert r.status_code == 200
>>> r.response
{
  "username": "yugokato",
  "role": "Senior Python SDET",
  "location": "Portland, OR",
  "specialties": [
    "Python",
    "Test Automation",
    "Framework Development",
    "Infrastructure & Tooling",
    "CI/CD"
  ],
  "status": "Automating everything"
}
```