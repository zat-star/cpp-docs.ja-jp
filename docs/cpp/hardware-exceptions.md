---
title: "ハードウェア例外 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "エラー [C++], ハードウェア"
  - "エラー [C++], 下位"
  - "例外, ハードウェア"
  - "ハードウェア例外"
  - "低レベル エラー"
ms.assetid: 06ac6f01-a8cf-4426-bb12-1688315ae1cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ハードウェア例外
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オペレーティング システムによって認識される標準例外のほとんどは、ハードウェア定義された例外です。  Windows はいくつかの低レベルのソフトウェア例外を認識しますが、それらは通常、オペレーティング システムで処理するのが適しています。  
  
 Windows は、異なるプロセッサのハードウェア エラーを、このセクションの例外コードにマップします。  場合によっては、プロセッサはこれらの例外のサブセットのみを生成します。  Windows は例外に関する情報を前処理して、適切な例外コードを発行します。  
  
 Windows で認識されるハードウェア例外を次の表にまとめました。  
  
|例外コード|例外の原因|  
|-----------|-----------|  
|**STATUS\_ACCESS\_VIOLATION**|アクセスできないメモリ位置に対する読み取りまたは書き込み。|  
|**STATUS\_BREAKPOINT**|ハードウェア定義されたブレークポイントに遭遇しました。デバッガーでのみ使用します。|  
|**STATUS\_DATATYPE\_MISALIGNMENT**|適切にアラインされていないアドレスにあるデータの読み取りまたは書き込み。たとえば、16 ビットのエンティティは 2 バイト境界上に配置する必要があります  \(Intel 80*x*86 プロセッサには適用されません\)。|  
|**STATUS\_FLOAT\_DIVIDE\_BY\_ZERO**|浮動小数点型の 0.0 による除算。|  
|**STATUS\_FLOAT\_OVERFLOW**|浮動小数点型の正の値の指数の最大値を超えています。|  
|**STATUS\_FLOAT\_UNDERFLOW**|浮動小数点型の負の値の指数の絶対値の最大値を超えています。|  
|**STATUS\_FLOATING\_RESEVERED\_OPERAND**|予約された浮動小数点形式を使用しています \(形式の無効な使用\)。|  
|**STATUS\_ILLEGAL\_INSTRUCTION**|プロセッサで定義されていない命令コードの実行を試みています。|  
|**STATUS\_PRIVILEGED\_INSTRUCTION**|現在のコンピューター モードでは、命令の実行が許可されていません。|  
|**STATUS\_INTEGER\_DIVIDE\_BY\_ZERO**|整数型の 0 による除算。|  
|**STATUS\_INTEGER\_OVERFLOW**|整数の範囲を超える演算を試みています。|  
|**STATUS\_SINGLE\_STEP**|シングル ステップ モードで 1 つの命令を実行しています。デバッガーでのみ使用されます。|  
  
 前の表に示した多くの例外は、デバッガーやオペレーティング システムなどの低レベルのコードで処理されることが前提となっています。  整数と浮動小数点数のエラーを除き、コードでこれらのエラーを処理しないでください。  したがって、通常は例外処理フィルターを使用して例外を無視 \(0 に評価\) してください。  そうしないと、下位レベルのしくみで適切に対応できなくなります。  ただし、[終了ハンドラーを記述](../cpp/writing-a-termination-handler.md)して、このような低レベルのエラーがもたらす潜在的な影響に対して適切な対策を講じることができます。  
  
## 参照  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)