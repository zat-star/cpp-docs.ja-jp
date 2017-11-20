---
title: "ctype_byname クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocale/std::ctype_byname
dev_langs: C++
helpviewer_keywords: ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f1fb3ef836361a4d98ac8c7ab764da5e3fd43c7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ctypebyname-class"></a>ctype_byname クラス
特定のロケールの ctype ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字を分類したり、大文字/小文字、ネイティブ、ロケールを指定して文字セットを変換したりできます。  
  
## <a name="syntax"></a>構文  
  
```
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```  
  
## <a name="remarks"></a>コメント  
 その動作は名前付きのロケール `_Locname` で決まります。 各コンストラクターは、[ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) または基底クラス `ctype<char>` の同等物でその基底オブジェクトを初期化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



