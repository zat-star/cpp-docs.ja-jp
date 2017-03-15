---
title: "テクニカル ノート 2: 永続オブジェクトのデータ形式 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive クラス, サポート (永続データの)"
  - "永続 C++ オブジェクト"
  - "永続オブジェクト データ"
  - "TN002"
  - "VERSIONABLE_SCHEMA マクロ"
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# テクニカル ノート 2: 永続オブジェクトのデータ形式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ファイルに格納されているオブジェクト データの永続的な C\+\+ オブジェクトと形式をサポートする MFC ルーチンについて説明します。  これは [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) と [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) マクロ クラスにのみ適用されます。  
  
## 問題  
 永続データ用の MFC 実装はファイルの一つの連続した一部の多くのオブジェクト データを格納します。  オブジェクトの `Serialize` メソッドのデバイスアプリケーションはバイナリ形式にオブジェクトのデータを変換します。  
  
 実装は、すべてのデータが同じで [CArchive クラス](../mfc/reference/carchive-class.md)形式で格納されることが保証されます。  これは変換として `CArchive` オブジェクトを使用します。  このオブジェクトが作成された時点から [CArchive::Close](../Topic/CArchive::Close.md)を呼び出すまで保持されます。  このメソッドは、プログラマによってプログラムの終了時 `CArchive`を含むスコープまたはデストラクターにより暗黙的明示的に呼び出すことができます。  
  
 ここでは `CArchive` のメンバー [CArchive::ReadObject](../Topic/CArchive::ReadObject.md) と [CArchive::WriteObject](../Topic/CArchive::WriteObject.md)の実装について説明します。  Arcobj.cpp のこれらの関数のコード、および Arccore.cpp の `CArchive` の主な実装を検索します。  ユーザー コードは `ReadObject` と `WriteObject` を直接呼び出さないでください。  代わりに、それらのオブジェクトは `DECLARE_SERIAL` と `IMPLEMENT_SERIAL` マクロによって自動的に生成されたクラス固有のタイプ セーフな挿入および抽出の演算子によって使用されます。  次のコードは `WriteObject` という暗黙的 `ReadObject` がどのようになるか:  
  
```  
class CMyObject : public CObject  
{  
    DECLARE_SERIAL(CMyObject)  
};  
  
IMPLEMENT_SERIAL(CMyObj, CObject, 1)  
  
// example usage (ar is a CArchive&)  
CMyObject* pObj;  
CArchive& ar;  
ar << pObj;        // calls ar.WriteObject(pObj)  
ar >> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))  
```  
  
## ストア \(CArchive::WriteObject\) への格納オブジェクト  
 メソッド `CArchive::WriteObject` はオブジェクトを構築するために使用されるヘッダー データを書き込みます。  このデータは、2 個の部分から成ります。: オブジェクトの種類およびオブジェクトの状態。  このメソッドはポインターの数に関係なく、一つのコピーだけを保存するように書き出されるそのオブジェクトへのオブジェクト ID を保持するためにも使用されます \(を含む円のポインター\)。  
  
 \(INSERT\) 保存し \(抽出\) 復元することで、複数の「マニフェスト定数にオブジェクトを使用します」。これらは、バイナリに格納され、アーカイブに重要な情報を提供する値です \(「w」プレフィックスを示す 16 ビット値は\) :  
  
|Tag|説明|  
|---------|--------|  
|wNullTag|null オブジェクト ポインター \(0\) に使用されます。|  
|wNewClassTag|参照クラスの説明このアーカイブのコンテキストに new \(\- 1\)。|  
|wOldClassTag|この読み込みコンテキスト \(0x8000\) でオブジェクトのクラスが参照されたことを示します。|  
  
 オブジェクトを保存すると、格納されたオブジェクトから 32 ビット永続的な識別 \(PID\) に対応している必要は [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) アーカイブ \(`m_pStoreMap`\) を保持します。  PID は、一意のオブジェクトおよびアーカイブのコンテキストで格納されている一意のクラス名に割り当てられます。  これらの PID は 1.時に配布順番に開始です。  これらの PID にアーカイブのスコープ外で重要度がないため、レコード番号または他の ID に特に項目と混同しないようにしてください。  
  
 `CArchive` クラスで、PID は 32 ビットですが、0x7FFE より大きい 16 ビットとして書き込まれます。  大きな PID は 32 ビット PID に続く 0x7FFF として表示されます。  これは、旧バージョンで作成されたプロジェクトの互換性が維持されます。  
  
 アーカイブにオブジェクトを格納する要求 \(通常はグローバルの出力ストリーム演算子を使用して\) の場合は、チェック [CObject](../Topic/CObject%20Class.md) の NULL ポインター用になります。  ポインターが NULL の場合、`wNullTag` はアーカイブのストリームに挿入されます。  
  
 ポインターが NULL ではなく、\(クラスは `DECLARE_SERIAL` クラス\) シリアル化できる場合、学生の平均オブジェクトが保存済みかどうかを参照する必要 `m_pStoreMap`。  一致するものがある場合、コードはアーカイブのストリームにオブジェクトに関連付けられた 32 ビット PID を挿入します。  
  
 オブジェクトが一度も保存されていない場合、考慮する 2 種類の可能性があります: オブジェクトの正確な型の両方 \(クラス\) は、このアーカイブのコンテキストに新規、またはオブジェクトによって参照される正確な型です。  型が参照されたかを確認するには、`CRuntimeClass` オブジェクトを格納するオブジェクトに関連付けられたに一致する [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトの `m_pStoreMap` を呼び出します。  一致する場合、`WriteObject` は `wOldClassTag` とこのインデックスのビットごとに `OR` のタグを挿入します。  `CRuntimeClass` がこのアーカイブのコンテキストを初めて使用する場合は、`WriteObject` はそのクラスに新しい PID を割り当て、`wNewClassTag` 値が付いたアーカイブに挿入します。  
  
 このクラスの記述子は `CRuntimeClass::Store` のメソッドを使用してアーカイブに挿入されます。  `CRuntimeClass::Store` は クラス \(以下を参照\) のスキーマ番号とクラス名の ASCII テキストを挿入します。  ASCII のテキスト名を使用して、アプリケーション間でアーカイブの一意性を保証しないことに注意してください。  したがって、破損を防ぐためにデータ ファイルに付ける必要があります。  クラス情報の挿入後に、アーカイブは `m_pStoreMap` にオブジェクトを挿入し、クラス固有のデータを挿入するに `Serialize` のメソッドを呼び出します。  `Serialize` を呼び出す前に `m_pStoreMap` にオブジェクトを配置するには、ストアへのオブジェクトの複数のコピーを保存することはできません。  
  
 最初の呼び出し元 \(通常はオブジェクトのネットワークのルート\) に戻った場合、[CArchive::Close](../Topic/CArchive::Close.md)を呼び出す必要があります。  [CFile](../mfc/reference/cfile-class.md)他の操作を実行する場合は、アーカイブの破損を防ぐために `CArchive` の [フラッシュ](../Topic/CArchive::Flush.md) メソッドを呼び出す必要があります。  
  
> [!NOTE]
>  この実装は、アーカイブのコンテキストごとの 0x3FFFFFFE インデックスのほど制限が適用されます。  この数値は、単一のアーカイブに格納できる単一のディスク ファイルがアーカイブのコンテキストの数を指定できます。クラスおよび一意のオブジェクトの最大数を表します。  
  
## ストア \(CArchive::ReadObject\) からの読み込みオブジェクト  
 \(抽出\) に読み込むには、`CArchive::ReadObject` メソッドを作成し、`WriteObject`の逆です。  `WriteObject`と同様に、`ReadObject` はユーザー コードで直接呼び出される; ユーザー コードが呼び出しと予想される `CRuntimeClass`の `ReadObject` タイプ セーフなストリーム演算子を呼び出す必要があります。  これは抽出操作の型の整合性が保証されます。  
  
 `WriteObject` の実装が増加する PID を割り当てたので、1 以降 \(0 は、null オブジェクト\) 定義され、`ReadObject` の実装がアーカイブのコンテキストの状態を維持するには、配列を使用できます。  PID がストアから読み込まれたとき、PID が `m_pLoadArray`の現在の上限を超える場合、`ReadObject` は新しいオブジェクト \(またはクラスの説明\) ことがわかっています。  
  
## スキーマ番号  
 クラスの `IMPLEMENT_SERIAL` のメソッドが見つかると、クラスに割り当てられたスキーマ番号は、クラスの実装の「バージョン」です。  スキーマのクラスは、指定したオブジェクトが永続的に行われた回数への実装 \(オブジェクト バージョンとして、参照される\)。  
  
 同じクラスの複数の異なる実装が時間の経過とともに保持する場合は、オブジェクトの `Serialize` メソッドの実装を変更するときにスキーマをインクリメントすると、実装の古いバージョンを使用して格納されたオブジェクトを読み込むためのコードを記述できます。  
  
 `CArchive::ReadObject` のメソッドは、メモリ クラスの説明スキーマ番号と異なる永続的なストアのスキーマ番号が見つかった場合 [CArchiveException](../mfc/reference/carchiveexception-class.md) をスローします。  この例外からは回復簡単ではありません。  
  
 スローされることからこの例外を保持する \(ビットごとのな `OR`\) スキーマ バージョンと組み合わせる `VERSIONABLE_SCHEMA` を使用できます。  `VERSIONABLE_SCHEMA`を使用すると、コードは [CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md)からの戻り値を調べることによって、`Serialize` 関数の適切なアクションを実行できます。  
  
## シリアル化するの直接呼び出し  
 多くの場合 `WriteObject` と `ReadObject` の一般的なオブジェクトのアーカイブ スキームのオーバーヘッドは必要ではありません。  これは [CDocument](../Topic/CDocument%20Class.md)にデータをシリアル化する一般的な例です。  この場合、`CDocument` の `Serialize` のメソッドは抽出または挿入演算子と、直接呼び出されます。  ドキュメントの内容が順番により一般的なオブジェクトのアーカイブ方式を使用することがあります。  
  
 `Serialize` を呼び出して直接次の長所と短所があります:  
  
-   補足バイトはアーカイブにオブジェクトをシリアル化する前または後に追加されません。  これはだけでなく、格納されたデータが小さくなりますが、ファイル形式を処理できる `Serialize` ルーチンを実装することができます。  
  
-   MFC が調整され、他の用途のより一般的なオブジェクトのアーカイブ スキーマを必要とする `WriteObject` と `ReadObject` の実装および関連コレクションはアプリケーションにリンクされません。  
  
-   古いコードはスキーマ番号から回復する必要はありません。  これは、または必要な識別子の数をデータ ファイルの先頭に使用する、ドキュメントのシリアル化コードをスキーマ番号、ファイル形式のバージョン番号をエンコードするために行うことができます。  
  
-   `Serialize` への直接呼び出しと `CArchive::GetObjectSchema` を使用して戻り値を処理してはならないシリアル化されているオブジェクト \(UINT\) \-バージョンが不明であることを示す 1。  
  
 `Serialize` がドキュメントに直接呼び出されるため、通常は、親ドキュメントへのアーカイブ参照へのドキュメントのサブオブジェクトが有効ではありません。  コンテナー ドキュメントにオブジェクトがポインターを明示的に指定してこれらのバック ポインターがアーカイブされる前に PID に `CDocument` のポインターをマップするために [CArchive::MapObject](../Topic/CArchive::MapObject.md) 関数を使用する必要があります。  
  
 前に説明したように、古いファイルの下位互換性を維持しながら `Serialize` を直接呼び出すと、バージョンとクラス情報を独自にエンコードすることで、書式を後で変更することができます。  `CArchive::SerializeClass` 関数は直接オブジェクトをシリアル化するか、基本クラスを呼び出す前に明示的に呼び出すことができます。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)