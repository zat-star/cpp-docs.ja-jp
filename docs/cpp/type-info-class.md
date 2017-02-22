---
title: "type_info Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "type_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス type_info"
  - "type_info クラス"
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# type_info Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**type\_info** クラスは、コンパイラによってプログラム内に生成される型情報を記述します。  このクラスのオブジェクトは、実質的には型の名前へのポインターを格納します。  **type\_info** クラスはまた、2 つの型の等価性または照合順序の比較に適したエンコード値を格納します。  型のエンコーディング規則と照合順序については指定されていないため、プログラムによって異なる場合があります。  
  
 **type\_info** クラスを使用するには、\<`typeinfo>` ヘッダー ファイルを含める必要があります。  **type\_info** クラスのインターフェイスは、次のとおりです。  
  
```  
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 **type\_info** クラスに存在するのがプライベート コピー コンストラクターのみであるため、このクラスのオブジェクトを直接インスタンス化することはできません。  **type\_info** \(一時\) オブジェクトを構築する唯一の方法は、[typeid](../cpp/typeid-operator.md) 演算子を使用することです。  代入演算子もプライベートであるため、**type\_info** クラスのオブジェクトのコピーや代入を行うことはできません。  
  
 **type\_info::hash\_code** は、**typeinfo** 型の値をインデックス値の分布にマッピングするために適したハッシュ関数を定義します。  
  
 `==` 演算子と `!=` 演算子は、それぞれ他の **type\_info** オブジェクトとの等価性または非等価性についての比較に使用できます。  
  
 型の照合順序と継承関係には関連性はありません。  型の照合順序は、**type\_info::before** メンバー関数を使用して決定します。  **type\_info::before** が異なるプログラムで同じ結果が得られる保証はなく、同じプログラムの異なる実行でさえ結果が異なる場合があります。  この点で、**type\_info::before** は、**\(&\)** 演算子のアドレスに似ています。  
  
 **type\_info::name** メンバー関数は、人間が判読可能な形式での型名を表す、null で終わる文字列への **const char\*** を返します。  ポイントされたメモリはキャッシュされ、直接解放されることはありません。  
  
 **type\_info::raw\_name** メンバー関数は、修飾された形式でのオブジェクト型名を表す、null で終わる文字列への **const char\*** を返します。  実際、名前は保存領域を節約するために、修飾された形式で格納されます。  したがって、この名前を使用した場合、名前の修飾を外す必要がないため **type\_info::name** よりも迅速に処理されます。  **type\_info::raw\_name** 関数から返された文字列は比較演算では使用できますが、読み取り可能ではありません。  人間が判読可能な文字列が必要な場合は、**type\_info::name** 関数を使用します。  
  
 型情報は、[\/GR \(ランタイム型情報を有効にする\)](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md) コンパイラ オプションが指定されている場合のみ生成されます。  
  
## 参照  
 [ランタイム型情報](../Topic/Run-Time%20Type%20Information.md)