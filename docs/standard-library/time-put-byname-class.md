---
title: "time_put_byname クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 719df3a10b7c4b72cc90b0a5f8aad247cf915f4d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="timeputbyname-class"></a>time_put_byname クラス
この派生テンプレート クラスは、型 `time_put`\< CharType, OutputIterator > のロケール ファセットとして使用できるオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Locname`  
 ロケール名。  
  
 `_Refs`  
 最初の参照数。  
  
## <a name="remarks"></a>コメント  
 その動作は [名前付きの](../standard-library/locale-class.md#name)ロケール `_Locname` で決まります。 各コンストラクターは、[time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator>( `_Refs`) を使用して、その基本オブジェクトを初期化します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



