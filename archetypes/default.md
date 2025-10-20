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
  
  # 2. LOCATION & BUSINESS FOCUS (High SEO Value)
  - "Kirksville MO"
  - "Kirksville Tech"
  - "Kirksville Computer Repair"
  - "Switchboard Tech Services"

  # 3. CORE SERVICES (Broad Appeal)
  - "computer repair"
  - "local tech support"
  - "website design"
  - "IT services"

  # 4. SPECIALTIES (Unique Selling Points)
  - "Linux systems"
  - "electronics repair"
  - "hardware restoration"

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
