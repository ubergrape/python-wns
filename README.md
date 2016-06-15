# python-wns
Python module for Windows Notification Service (WNS) for Windows tablets/phones(8+)

## INSTALL

```
pip install python-wns
```

## EXAMPLE

```python
from python-wns import WNSClient

wns = WNSClient('wnsclientid':  '123','wnsclientsecret': 'xyz')
token = 'b5bb9d8014a0f9b1d61e21e796d78dccdf1352f23cd32812f4850b87'

# Send toast notification
message = {'type': 'toast', 'text': ['Hello World!']}
wns.process(token=token, message=message)

# Send tile notification
message = {
    'type': 'tile',
    'tiles': [
        {
            'template': 'TileSquare71x71IconWithBadge',
            'image': ['../Assets/badge-icons/SmallTileBadgeIcon.png']
        },
        {
            'template': 'TileSquare150x150IconWithBadge',
            'image': ['../Assets/badge-icons/MediumTileBadgeIcon.png'],
        },
        {
            'type': 'tile',
            'template': 'TileWide310x150IconWithBadgeAndText',
            'image': ['../Assets/badge-icons/MediumTileBadgeIcon.png'],
            'text': ['Hello World', 'second line', 'third line'],
        }
    ]
}
wns.process(token=token, message=message)
```
