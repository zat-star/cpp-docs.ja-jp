---
title: "ComPtr::As メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As メソッド"
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtr::As メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたテンプレート パラメーターで識別されるインターフェイスを表す ComPtr オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 パラメーターで表されるインターフェイス `p`します。  
  
 `p`  
 パラメーターで指定されたインターフェイスを表す ComPtr オブジェクト `U`します。 パラメーター `p` 現在の ComPtr オブジェクトを参照する必要があります。  
  
## <a name="remarks"></a>コメント  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートなど、C++ 言語の機能をサポートする、内部のヘルパー特殊である、 [自動](../cpp/auto-cpp.md) 推論キーワードを入力します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>「  
 [ComPtr クラス](../windows/comptr-class.md)