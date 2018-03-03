---
title: "リンカ ツール エラー LNK1312 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7f7b57512f58402403a50bf57176f975769573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1312"></a>リンカ ツール エラー LNK1312
ファイルが無効か破損しています: アセンブリをインポートできません。  
  
 アセンブリ、モジュールまたはしてコンパイルされたアセンブリではないファイルを作成するときに**/clr**に渡された、 **/ASSEMBLYMODULE**リンカー オプション。  オブジェクト ファイルが渡された場合**/ASSEMBLYMODULE**、のみ、オブジェクトに直接渡す、リンカーの代わりを**/ASSEMBLYMODULE**です。  
  
## <a name="example"></a>例  
 次の例では、.obj ファイルを作成します。  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>例  
 次の例では、LNK1312 が生成されます。  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```