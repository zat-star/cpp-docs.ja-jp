---
title: _ _raise |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __raise
- __raise_cpp
dev_langs:
- C++
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93bd00c89df69d655f42c06509ef0360eff0c092
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="raise"></a>__raise
イベントの呼び出しサイトを強調します。  
  
## <a name="syntax"></a>構文  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## <a name="remarks"></a>コメント  
 マネージ コードからは、イベントが定義されたクラス内からのみイベントを発生させることができます。 参照してください[イベント](../windows/event-cpp-component-extensions.md)詳細についてはします。  
  
 キーワード `__raise` は、非イベントを呼び出すときにエラーを生成します。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## <a name="example"></a>例  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [イベント処理](../cpp/event-handling.md)   
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)