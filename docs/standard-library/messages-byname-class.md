---
title: "messages_byname クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- messages_byname
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 014346887441678f53872aa7b791931e89361a5c
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="messagesbyname-class"></a>messages_byname クラス
特定のロケールのメッセージ ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。ローカライズされたメッセージを取得できるようにします。  
  
## <a name="syntax"></a>構文  
  
```
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Locname`  
 名前付きのロケール。  
  
 `_Refs`  
 最初の参照数。  
  
## <a name="remarks"></a>コメント  
 その動作は名前付きのロケール `_Locname` で決まります。 各コンストラクターは、[messages](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




