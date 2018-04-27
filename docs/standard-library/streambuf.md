---
title: '&lt;streambuf&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84b8e370da8e717e7d941cbae8de0637d1eb74da
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

テンプレート クラス [basic_streambuf](../standard-library/basic-streambuf-class.md) を定義する iostreams の標準ヘッダー \<streambuf> を含みます。このテンプレート クラスは iostreams クラスの操作の基本になります。 通常、このヘッダーは別の iostream ヘッダーにインクルードされているため、ユーザーが直接インクルードする必要はありません。

## <a name="syntax"></a>構文

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|`char` を使用する `basic_streambuf` をテンプレート パラメーターとして特化したクラス。|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|`wchar_t` を使用する `basic_streambuf` をテンプレート パラメーターとして特化したクラス。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_streambuf クラス](http://msdn.microsoft.com/en-us/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|このテンプレート クラスは、ストリームの特定の表現との相互間での要素の伝送を制御する、ストリーム バッファーを派生させるための抽象基底クラスについて説明します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
