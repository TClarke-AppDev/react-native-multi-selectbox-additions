# react-native-multi-selectbox

Platform independent (Android / iOS) Selectbox | Picker | Multi-select | Multi-picker. The idea is to bring out the common user-interface & user-experience on both platforms.

![demo](https://raw.githubusercontent.com/sauzy34/react-native-multi-selectbox/master/demo.gif)

## Getting started

### How to install 🎹

### `npm install git+https://github.com/TClarke-AppDev/react-native-multi-selectbox-additions`

or

### `yarn add git+https://github.com/TClarke-AppDev/react-native-multi-selectbox-additions`

### Usage 𖣠

```
import React, { useState } from 'react'
import { Text, View } from 'react-native'
import SelectBox from 'react-native-multi-selectbox'
import { xorBy } from 'lodash'

// Options data must contain 'item' & 'id' keys

const K_OPTIONS = [
  {
    item: 'Juventus',
    id: 'JUVE',
  },
  {
    item: 'Real Madrid',
    id: 'RM',
  },
  {
    item: 'Barcelona',
    id: 'BR',
  },
  {
    item: 'PSG',
    id: 'PSG',
  },
  {
    item: 'FC Bayern Munich',
    id: 'FBM',
  },
  {
    item: 'Manchester United FC',
    id: 'MUN',
  },
  {
    item: 'Manchester City FC',
    id: 'MCI',
  },
  {
    item: 'Everton FC',
    id: 'EVE',
  },
  {
    item: 'Tottenham Hotspur FC',
    id: 'TOT',
  },
  {
    item: 'Chelsea FC',
    id: 'CHE',
  },
  {
    item: 'Liverpool FC',
    id: 'LIV',
  },
  {
    item: 'Arsenal FC',
    id: 'ARS',
  },

  {
    item: 'Leicester City FC',
    id: 'LEI',
  },
]

function App() {
  const [selectedTeam, setSelectedTeam] = useState({})
  const [selectedTeams, setSelectedTeams] = useState([])
  return (
    <View style={{ margin: 30 }}>
      <View style={{ width: '100%', alignItems: 'center' }}>
        <Text style={{ fontSize: 30, paddingBottom: 20 }}>Demos</Text>
      </View>
      <Text style={{ fontSize: 20, paddingBottom: 10 }}>Select Demo</Text>
      <SelectBox
        label="Select single"
        options={K_OPTIONS}
        value={selectedTeam}
        onChange={onChange()}
        hideInputFilter={false}
      />
      <View style={{ height: 40 }} />
      <Text style={{ fontSize: 20, paddingBottom: 10 }}>MultiSelect Demo</Text>
      <SelectBox
        label="Select multiple"
        options={K_OPTIONS}
        selectedValues={selectedTeams}
        onMultiSelect={onMultiChange()}
        onTapClose={onMultiChange()}
        isMulti
      />
    </View>
  )

  function onMultiChange() {
    return (item) => setSelectedTeams(xorBy(selectedTeams, [item], 'id'))
  }

  function onChange() {
    return (val) => setSelectedTeam(val)
  }
}

export default App


```

| Prop                      |     Type     |                                                                                                                                                        Default Value |
| ------------------------- | :----------: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| label                     |    String    |                                                                                                                                                                Label |
| inputPlaceholder          |    string    |                                                                                                                                                                Label |
| listEmptyText                     |    String    |                                                                                                                                                                "No results found" |
| width                     |    string    |                                                                                                                                                               "100%" |
| viewMargin                |    string    |                                                                                                                                                                "0px" |
| isMulti                   |   boolean    |                                                                                                                                                                false |
| hideInputFilter           |   boolean    |                                                                                                                                                                 true |
| selectedValues            |    array     |                                                                                                                                                                   [] |
| value                     |    array     |                                                                                                                                                                   [] |
| selectIcon                |  component   |                                                                                                                                          <Icon name={'downArrow'} /> |
| labelStyle                | style object |                                                                                                                                                        Default style |
| containerStyle            | style object |                                                                                                                                                        Default style |
| inputFilterContainerStyle | style object |                                                                                                                                                        Default style |
| inputFilterStyle          | style object |                                                                                                                                                        Default style |
| optionsLabelStyle         | style object |                                                                                                                                                        Default style |
| optionContainerStyle      | style object |                                                                                                                                                        Default style |
| multiOptionContainerStyle | style object |                                                                                                                                                        Default style |
| multiOptionsLabelStyle    | style object |                                                                                                                                                        Default style |
| multiListEmptyLabelStyle  | style object |                                                                                                                                                        Default style |
| listEmptyLabelStyle       | style object |                                                                                                                                                        Default style |
| selectedItemStyle         | style object |                                                                                                                                                        Default style |
searchInputProps         | object |                                                                                                                                                        Default props |
multiSelectInputFieldProps         | object |                                                                                                                                                        Default props |
| listOptionProps          | object |      Default props |
| arrowIconColor         | color string |                                                                                                                                                        Default primary color |
| searchIconColor         | color string |                                                                                                                                                        Default primary color |
| toggleIconColor         | color string |                                                                                                                                                        Default primary color |
| options                   |    array     | `[{ item: 'Juventus', id: 'JUVE'},{ item: 'Real Madrid', id: 'RM'},{ item: 'Barcelona', id: 'BR'},{ item: 'PSG', id: 'PSG'},{ item: 'FC Bayern Munich', id: 'FBM'}]` |
| onExpand | callback | Returns if the flatlist is visible or hidden on open/close |

## Support & Share 💆🏼‍♂️

Original Source: [Repo](https://github.com/sauzy34/react-native-multi-selectbox)

Please star that repository on Github to enhance the reach to more developers and give support to the original creator.
