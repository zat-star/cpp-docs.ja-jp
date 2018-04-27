---
title: 入力ストリーム オブジェクトのコンストラクト | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a63ba3d8e54e416313ec24d7455ca4cf70979b9f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="constructing-input-stream-objects"></a>入力ストリーム オブジェクトのコンストラクト

`cin` オブジェクトのみを使う場合は、入力ストリームをコンストラクトする必要はありません。 次のものを使う場合は、入力ストリームをコンストラクトする必要があります。

- [入力ファイル ストリーム コンストラクター](#vclrfinputfilestreamconstructorsanchor8)

- [入力文字列ストリーム コンストラクター](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> 入力ファイル ストリーム コンストラクター

入力ファイル ストリームは、2 つの方法で作成できます。

- `void` 引数コンストラクターを使った後、`open` メンバー関数を呼び出します。

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- コンストラクターの呼び出しでファイル名とモード フラグを指定し、それによってコンストラクション プロセスの間にファイルを開きます。

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> 入力文字列ストリーム コンストラクター

入力文字列ストリーム コンストラクターには、事前に割り当てられて初期化された記憶域のアドレスが必要です。

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)<br/>
