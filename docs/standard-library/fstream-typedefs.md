---
title: '&lt;fstream&gt; typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 55a148c472048c5531521cd6f4574477e7c31cac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs
||||  
|-|-|-|  
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|  
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|  
|[wifstream](#wifstream)|[wofstream](#wofstream)|  
  
##  <a name="filebuf"></a>  filebuf  
 `char` テンプレート パラメーターに特殊化された型 `basic_filebuf`。  
  
```
typedef basic_filebuf<char, char_traits<char>> filebuf;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_filebuf](../standard-library/basic-filebuf-class.md) の同意語で、既定の文字の特性を持つ型 `char` の要素に対して特殊化されています。  
  
##  <a name="fstream">fstream</a>  
 `char` テンプレート パラメーターに特殊化された型 `basic_fstream`。  
  
```
typedef basic_fstream<char, char_traits<char>> fstream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_fstream`char` の同意語で、既定の文字の特性を持つ型 ](../standard-library/basic-fstream-class.md) の要素に対して特殊化されています。  
  
##  <a name="ifstream"></a>  ifstream  
 ファイルから 1 バイト文字のデータを順番に読み取るために使用するストリームを定義します。 `ifstream` は、テンプレート クラス `basic_ifstream` を `char` に対して特殊化した typedef です。  
  
 なお、`wifstream` 2 ワイド文字を読み取るように `basic_ifstream` を特殊化した `wchar_t` という typedef もあります。 詳細については、「[wifstream](../standard-library/fstream-typedefs.md#wifstream)」を参照してください。  
  
```
typedef basic_ifstream<char, char_traits<char>> ifstream;
```  
  
### <a name="remarks"></a>コメント  
 型はテンプレート クラス `basic_ifstream` のシノニムで、既定の特性を持つ型 char の要素に対して特殊化されています。 次に例を示します。  
  
 `using namespace std;`  
  
 `ifstream infile("existingtextfile.txt");`  
  
 `if (!infile.bad())`  
  
 `{`  
  
 `// Dump the contents of the file to cout.`  
  
 `cout << infile.rdbuf();`  
  
 `infile.close();`  
  
 `}`  
  
##  <a name="ofstream"></a>  ofstream  
 `char` テンプレート パラメーターに特殊化された型 `basic_ofstream`。  
  
```
typedef basic_ofstream<char, char_traits<char>> ofstream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_ofstream](../standard-library/basic-ofstream-class.md) の同意語で、既定の文字の特性を持つ型 `char` の要素に対して特殊化されています。  
  
##  <a name="wfstream"></a>  wfstream  
 `wchar_t` テンプレート パラメーターに特殊化された型 `basic_fstream`。  
  
```
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_fstream](../standard-library/basic-fstream-class.md) の同意語で、既定の文字の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
##  <a name="wifstream"></a>  wifstream  
 `wchar_t` テンプレート パラメーターに特殊化された型 `basic_ifstream`。  
  
```
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_ifstream](../standard-library/basic-ifstream-class.md) の同意語で、既定の文字の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
##  <a name="wofstream"></a>  wofstream  
 `wchar_t` テンプレート パラメーターに特殊化された型 `basic_ofstream`。  
  
```
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_ofstream](../standard-library/basic-ofstream-class.md) の同意語で、既定の文字の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
##  <a name="wfilebuf"></a>  wfilebuf  
 `wchar_t` テンプレート パラメーターに特殊化された型 `basic_filebuf`。  
  
```
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_filebuf](../standard-library/basic-filebuf-class.md) の同意語で、既定の文字の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
## <a name="see-also"></a>参照  
 [\<fstream>](../standard-library/fstream.md)



