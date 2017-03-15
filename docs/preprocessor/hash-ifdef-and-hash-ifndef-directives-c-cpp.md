---
title: "#ifdef および #ifndef ディレクティブ (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#ifndef"
  - "#ifdef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#ifdef ディレクティブ"
  - "#ifndef ディレクティブ"
  - "ifdef ディレクティブ (#ifdef)"
  - "ifndef ディレクティブ (#ifndef)"
  - "プリプロセッサ, ディレクティブ"
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #ifdef および #ifndef ディレクティブ (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#ifdef** および **\#ifndef** ディレクティブは、`#if` ディレクティブを **defined**\( *identifier* \) と組み合わせて使用した場合と同じタスクを実行します。  
  
## 構文  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## 解説  
 **\#ifdef** および **\#ifndef** ディレクティブは、`#if` を使用できるいずれの場所でも使用できます。  **\#ifdef** *identifier* ステートメントは、*identifier* を定義している場合の `#if 1` に相当します。また、*identifier* を定義していないか、その定義を `#undef` ディレクティブで削除した場合の `#if 0` に相当します。  これらのディレクティブは、C または C\+\+ ソース コードで宣言された識別子ではなく、`#define` で定義された識別子の有無を調べます。  
  
 これらのディレクティブは、言語の以前のバージョンとの互換性を維持するために用意されています。  **defined\(** *identifier* **\)** 定数式を `#if` ディレクティブと組み合わせて使用することをお勧めします。  
  
 **\#ifndef** ディレクティブは、**\#ifdef** が調べる反対の条件を調べます。  識別子を定義していない \(またはその定義を `#undef` で削除した\) 場合、条件は true \(ゼロ以外\) です。  それ以外の場合、条件は False \(0\) です。  
  
 **Microsoft 固有の仕様 →**  
  
 *identifier* は \/D オプションを使用してコマンド ラインから渡すことができます。  最大 30 個のマクロを \/D に指定できます。  
  
 定義をコマンド ラインから渡すことができるため、定義の有無を調べるために便利です。  次に例を示します。  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)