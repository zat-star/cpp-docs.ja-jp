---
title: "シリアル化 : シリアル化可能なクラスの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 派生"
  - "CObject クラス, 派生 (シリアル化できるクラスを)"
  - "コンストラクター [C++], 定義 (引数なし)"
  - "DECLARE_SERIAL マクロ"
  - "既定のコンストラクター"
  - "既定 [C++], コンストラクター"
  - "IMPLEMENT_SERIAL マクロ"
  - "既定のコンストラクターがない"
  - "引数なしコンストラクター"
  - "シリアル化できるクラス"
  - "シリアル化 [C++], シリアル化できるクラス"
  - "Serialize メソッド, オーバーライド"
  - "VERSIONABLE_SCHEMA マクロ"
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# シリアル化 : シリアル化可能なクラスの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

5 個の主要手順がクラスをシリアル化可能にする必要があります。  こうしたプロパティは、次の一覧に、次のセクションで説明する場合:  
  
1.  [CObject からクラスを派生すること](#_core_deriving_your_class_from_cobject) \(または `CObject`から派生したクラスの一部\)。  
  
2.  [シリアル化するのメンバー関数のオーバーライド](#_core_overriding_the_serialize_member_function)。  
  
3.  クラス宣言の[DECLARE\_SERIAL マクロを使用します。](#_core_using_the_declare_serial_macro)。  
  
4.  [引数を受け取らないコンストラクターを定義します](#_core_defining_a_constructor_with_no_arguments)。  
  
5.  クラスの[実装ファイルの IMPLEMENT\_SERIAL マクロを使用して](#_core_using_the_implement_serial_macro_in_the_implementation_file)。  
  
 [CArchive](../mfc/reference/carchive-class.md)と演算子を使わず `Serialize` を \>\> 直接 \<\< 呼び出すと、最後の手順 3 はシリアル化に必要はありません。  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> CObject からクラスを派生すること  
 基本的なシリアル化プロトコルと機能は `CObject` クラスに定義されます。  クラス `CPerson`の次の宣言に示すように、`CObject` からクラス \(または `CObject`から派生したクラス\) から派生することで、`CObject`のシリアル化のプロトコルと機能にアクセスするために使用できます。  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> シリアル化するのメンバー関数のオーバーライド  
 `CObject` クラスで定義されて `Serialize` のメンバー関数が実際にオブジェクトの現在の状態を取得するために必要なデータをシリアル化する必要があります。  `Serialize` 関数を読み取るために使用される、オブジェクト データを書き込みます `CArchive` の引数。  [CArchive](../mfc/reference/carchive-class.md) オブジェクトに `Serialize` \(データの書き込み\) に格納したり、読み込んでいるかどうかを示すメンバー関数、`IsStoring`があります \(データの読み取り\)。  ガイドとして `IsStoring` の結果を使用して、ストリーム演算子 \(**\>\>**\) の出力ストリーム演算子 \(**\<\<**\) またはデータを抽出するの `CArchive` オブジェクトでオブジェクト データを挿入します。  
  
 `CObject` から派生され、2 種類の新しいメンバー変数の型 `CString` と **WORD**クラスについて考えます。  次のクラス宣言のフラグメントは `Serialize` のオーバーライドされたメンバー関数の新しいメンバー変数と宣言を示します:  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_1.h)]  
  
#### シリアル化するのメンバー関数をオーバーライドするには  
  
1.  オブジェクトの継承された部分がシリアル化されるようにするに `Serialize` の基本クラス バージョンを呼び出します。  
  
2.  クラスに固有のメンバー変数を追加または取得します。  
  
     挿入および抽出の演算子がアーカイブ クラスとデータの読み取りと書き込みのために対話します。  次の例は、上に宣言された `CPerson` クラスの `Serialize` を実装する方法を示します。:  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_2.cpp)]  
  
 また、大量の型指定されていないデータの読み書きに [CArchive::Read](../Topic/CArchive::Read.md) と [CArchive::Write](../Topic/CArchive::Write.md) メンバー関数を使用できます。  
  
##  <a name="_core_using_the_declare_serial_macro"></a> DECLARE\_SERIAL マクロを使用します。  
 `DECLARE_SERIAL` マクロは、シリアル化をサポートするクラスの宣言に、次に示すように、必要があります:  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> 引数なしのコンストラクターの定義  
 MFC は逆シリアル化されているオブジェクトを再作成するときの既定のコンストラクターが必要です \(ディスクから読み込まれて\)。  シリアル化解除はオブジェクトを再作成するために必要な値のすべてのメンバー変数を指定します。  
  
 このコンストラクターは、プライベート宣言されたパブリック、Protected である場合があります。  protected またはプライベートな、シリアル化を行う関数だけで使用されることを確認できます。  コンストラクターは、必要に応じて削除するその状態にオブジェクトを配置する必要があります。  
  
> [!NOTE]
>  `DECLARE_SERIAL` と `IMPLEMENT_SERIAL` マクロを使用してクラスの引数を持たないコンストラクターが定義されていない場合、「既定のコンストラクターに `IMPLEMENT_SERIAL` マクロが使用されている行に使用できる」コンパイラの警告を回避できます。  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> 実装ファイルの IMPLEMENT\_SERIAL マクロを使用して  
 `CObject`からシリアル化できるクラスを派生すると `IMPLEMENT_SERIAL` マクロが必要な各種関数を定義するために使用されます。  実装ファイル \(.cpp\) でクラスにこのマクロを使用します。  マクロに最初の 2 番目の引数は、クラスの名前と、その直接の基本クラスの名前です。  
  
 このマクロに 3 番目の引数はスキーマ番号です。  スキーマ番号は主にクラスのオブジェクトのバージョン番号です。  整数を超える使用したり、スキーマ番号の 0 に設定します。\(データベース用語でこのスキーマ番号を混同しないでください。  
  
 オブジェクトをメモリに読み込むときに MFC のシリアル化コード チェック スキーマ番号。  ディスク上のオブジェクトのスキーマ番号がメモリ クラスのスキーマ番号に一致する、プログラムがオブジェクトの正しいバージョンを読み込むことができない `CArchiveException`をスローします。  
  
 `Serialize` のメンバー関数の複数のバージョン \(アプリケーションの各バージョンで記述された、つまりファイル読めれば—場合 `IMPLEMENT_SERIAL` マクロに引数として値 **VERSIONABLE\_SCHEMA** を使用できます。  使用方法の例については、`CArchive`クラスの `GetObjectSchema` メンバー関数を参照してください。  
  
 次の例に `CObject`から派生されるクラスに `IMPLEMENT_SERIAL`、`CPerson`の使用方法を説明しています:  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_4.cpp)]  
  
 シリアル化できるクラスがある場合は、文書 [シリアル化: オブジェクトのシリアル化](../Topic/Serialization:%20Serializing%20an%20Object.md)"に説明されているように、クラス オブジェクトをシリアル化できます。  
  
## 参照  
 [シリアル化](../Topic/Serialization%20in%20MFC.md)