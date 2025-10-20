---
title: "{{ replace .File.ContentBaseName `-` ` ` | title }}"
date: {{ .Date }}
lastmod: {{ .Date }} 
draft: false 

# -----------------
# CORE SEO FIELDS
# -----------------
description: "" # Aim for 150-160 characters. This is the search snippet.
slug: "{{ .File.ContentBaseName }}" # Ensures a clean, predictable URL path.

keywords: 
  # 1. GENERATED (Kept for relevancy to post slug)
  - "{{ replace .File.ContentBaseName `-` ` ` | lower }}" 
  
  # 2. CORE PROJECT & SUBJECT MATTER
  - "Scrollmapper"
  - "scripture analysis"
  - "bible databases"
  - "extra-biblical texts"
  - "deuterocanonical"
  
  # 3. RESEARCH & FEATURES
  - "cross-reference"
  - "textual analysis"
  - "Gephi integration"
  - "data visualization"


  
# -----------------
# CONTENT METADATA
# -----------------
author: "Leo Blanchette" # Set your default author here.
cover: "" # Path to the featured image for the post (e.g., /images/post-name/featured.jpg).
toc: true # Table of Contents (if supported by your theme).
weight: 0 # Used for ordering content lists (higher weight = appears earlier).
type: "post" # Defines the content type for template lookup.
---

## Introduction

This is the start of your SEO-optimized article.
