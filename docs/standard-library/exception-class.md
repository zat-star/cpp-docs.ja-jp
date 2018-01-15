---
title: "exception クラス | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception
dev_langs: C++
helpviewer_keywords: exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33e6d0ed3153b31c231790610de1a7c4da1a94ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exception-class"></a>exception クラス
このクラスは、特定の式と C++ 標準ライブラリによってスローされたすべての例外の基底クラスとして機能します。  
  
## <a name="syntax"></a>構文  
```  
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };  
``` 
## <a name="remarks"></a>コメント  
 具体的には、この基底クラスは [\<stdexcept >](../standard-library/stdexcept.md) で定義されている標準的な例外クラスのルートです。 `what` によって返される C の文字列値は、既定のコンストラクターによって未指定のまま残されますが、特定の派生クラスのコンストラクターによって実装定義された C の文字列として定義される場合があります。 このメンバー関数は、いずれも例外をスローしません。  
  
 `int` パラメーターでは、メモリを割り当てる必要がないことを指定できます。 `int` の値は無視されます。  
  
> [!NOTE]
>  コンストラクター `exception(const char* const &message)` と `exception(const char* const &message, int)` は、C++ 標準ライブラリに対する Microsoft 拡張機能です。  
  
## <a name="example"></a>例  
 `exception` クラスから継承する標準の例外クラスの使用例については、[\<stdexcept>](../standard-library/stdexcept.md) で定義されているクラスを参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<exception>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



