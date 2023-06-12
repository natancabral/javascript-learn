## Reduce Names
> return string 
#### Less Name

```js
function reduceFullName(name: string, MAX_LENGTH: number, removeLinkNames: boolean) {
  if (removeLinkNames) {
    name = name.replace(/ da | das | de | do | dos /gi, ' ');
  }

  const clear = (str) => String(str).replace(/\s+/g, ' ').trim(); 
  let clearName = clear(name);
  let diff = clearName.length - MAX_LENGTH;
  let arr = clearName.split(' ');
  let firstName, lastName;

  // remove names
  // TODO: maybe or not
  if (arr.length > 6) {
    firstName = arr.slice(0, 2);
    lastName = arr.slice(5);
    arr = [ ...firstName, ...lastName];
    clearName = arr.join(' ');
    diff = clearName.length - MAX_LENGTH;
  }

  // verify length
  if (clearName.length <= MAX_LENGTH) {
    return clearName;
  }

  // sort
  const sortByLength = arr.slice(2).sort(function(a, b){
    // ASC  -> a.length - b.length
    // DESC -> b.length - a.length
    return b.length - a.length;
  });

  // verify long names
  const needReplaceNames: string[] = [];
  sortByLength.forEach((item: string) => {
    const letterDotsAndSpaces = needReplaceNames.length * 2;
    const len = needReplaceNames.join('').length - letterDotsAndSpaces;
    if (len >= diff) return;
    needReplaceNames.push(item);
  });

  // replace long names
  const reduceName = arr.reduce((acc: string, cur: string, index: number) => {
    if (needReplaceNames.includes(cur)) {
      cur = String(cur).substring(0, 1).toUpperCase() + '.'
    }
    return `${acc} ${cur}`;
  }, '');

  const final = clear(reduceName);
  // console.log({ final, len: final.length });
  return final;
}
```

#### Remove Special Chars

```js
function removeSpecialChars (str: string) {
  if (!str) return '';
  str = String(str).normalize('NFD');
  str = String(str).replace(/[\u0300-\u036f]/g, '');
  str = String(str).replace(/[\"\`\'\']/gi,'');
  str = String(str).replace(/[\-\_\—]/gi,'');
  return str.trim();
}
```
