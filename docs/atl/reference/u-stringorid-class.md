---
title: "_U_STRINGorID クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL._U_STRINGorID"
  - "ATL::_U_STRINGorID"
  - "_U_STRINGorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_STRINGorID クラス"
  - "U_STRINGorID クラス"
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_STRINGorID クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この引数アダプター クラスによって、呼び出し元で **MAKEINTRESOURCE** マクロを使用して ID を文字列に変換せずに、リソース名 \(`LPCTSTR`\) またはリソース ID \(**UINT**\) を関数に渡すことができます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class _U_STRINGorID  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[\_U\_STRINGorID::\_U\_STRINGorID](../Topic/_U_STRINGorID::_U_STRINGorID.md)|コンストラクターです。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[\_U\_STRINGorID::m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md)|リソース識別子。|  
  
## 解説  
 このクラスは、リソースの名前または ID である可能性がある `LPCTSTR` の引数を受け取る [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042)、[LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072)と [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) 関数などの Windows リソース管理 API に対するラッパーを実行するようにデザインされています  
  
 クラスは 2 種類のコンストラクター オーバーロードを定義します: 1 つが `LPCTSTR` の引数を受け取り、そのほかのは **uint** の引数を受け取ります。  **uint** の引数は、クラスの一つのデータ メンバー、[m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md)に格納されている **MAKEINTRESOURCE** マクロと結果を使用して Windows の管理機能と互換性のあるリソースの種類に変換されます。  `LPCTSTR` のコンストラクターへの引数は変換されずに格納されます。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)