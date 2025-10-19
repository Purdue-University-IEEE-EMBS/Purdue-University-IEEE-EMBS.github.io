---
title: Photo Gallery
nav_order: 7
---

# **EMBS Photo Gallery**

Here are some photos taken from some of the different events, meetings, and activities that we have done as a club.

---

### **EMBS Club Meetings**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/meetings'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

***

### **Cook Medical Tour**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/cook_medical_tour'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

***

### **EMBS Team Dinners**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/team_dinner'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

***

### **EMBS Prosthetics Workshop**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/embs_prosthetics_workshop'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

***

### **EMBS Research Presentations**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/poster_presentation'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

***

### **EMBS Conferences**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/conference'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

***

### **EMBS Devices**

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/assets/images/photo_gallery/devices_testing'" %}
{% assign gallery = gallery | sort: "path" %}

<div class="gallery">
  {% for image in gallery %}
  <a href="{{ image.path | relative_url }}" data-lightbox="gallery">
    <img src="{{ image.path | relative_url }}" alt="Gallery image">
  </a>
  {% endfor %}
</div>

<!-- Lightbox2 (click-to-enlarge for gallery) -->
<link href="https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.3/css/lightbox.min.css" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.3/js/lightbox.min.js"></script>

<style>
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
}

.gallery img {
  height: 180px; /* all images same height */
  width: auto;   /* width adjusts automatically */
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 1px 4px rgba(0,0,0,0.15);
  transition: transform 0.2s ease-in-out;
  border: 1px solid var(--color-border-muted);
}

.gallery img:hover {
  transform: scale(1.03);
}
</style>
