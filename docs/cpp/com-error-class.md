---
title: "_com_error クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error クラス"
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_com_error` オブジェクトは、タイプ ライブラリから生成されるヘッダー ファイル内のエラー処理ラッパー関数によって、またはいずれかの COM サポート クラスによって検出される例外条件を表します。  `_com_error` クラスは、`HRESULT` エラー コードと、関連する任意の `IErrorInfo Interface` オブジェクトをカプセル化します。  
  
### 構築  
  
|||  
|-|-|  
|[\_com\_error](../cpp/com-error-com-error.md)|`_com_error` オブジェクトを構築します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../cpp/com-error-operator-equal.md)|既存の `_com_error` オブジェクトを別のオブジェクトに割り当てます。|  
  
### 抽出関数  
  
|||  
|-|-|  
|[Error](../Topic/_com_error::Error.md)|コンストラクターに渡された `HRESULT` を取得します。|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。|  
|[WCode](../cpp/com-error-wcode.md)|カプセル化された `HRESULT` にマップされた 16 ビット エラー コードを取得します。|  
  
### IErrorInfo の関数  
  
|||  
|-|-|  
|[説明](../cpp/com-error-description.md)|`IErrorInfo::GetDescription` 関数を呼び出します。|  
|[HelpContext](../cpp/com-error-helpcontext.md)|`IErrorInfo::GetHelpContext` 関数を呼び出します。|  
|[HelpFile](../Topic/_com_error::HelpFile.md)|`IErrorInfo::GetHelpFile` 関数を呼び出します。|  
|[Source](../cpp/com-error-source.md)|`IErrorInfo::GetSource` 関数を呼び出します。|  
|[GUID](../cpp/com-error-guid.md)|`IErrorInfo::GetGUID` 関数を呼び出します。|  
  
### 書式メッセージの抽出  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|`_com_error` オブジェクトに格納された HRESULT の文字列メッセージを取得します。|  
  
### ExepInfo.wCode と HRESULT のマッパー  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32 ビットの `HRESULT` を 16 ビットの `wCode` にマップします。|  
|[WCodeToHRESULT](../Topic/_com_error::WCodeToHRESULT.md)|16 ビットの `wCode` を 32 ビットの `HRESULT` にマップします。|  
  
## END Microsoft 固有の仕様  
  
## 要件  
 `Header:` comdef.h  
  
 `Lib:` comsuppw.lib または comsuppwd.lib \(詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照\)  
  
## 参照  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo Interface](http://msdn.microsoft.com/ja-jp/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)