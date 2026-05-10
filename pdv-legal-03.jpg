const navToggle = document.querySelector('.nav-toggle');
const mainNav = document.querySelector('.main-nav');

if (navToggle && mainNav) {
  navToggle.addEventListener('click', () => {
    const isOpen = mainNav.classList.toggle('open');
    navToggle.setAttribute('aria-expanded', String(isOpen));
  });

  mainNav.querySelectorAll('a').forEach((link) => {
    link.addEventListener('click', () => {
      mainNav.classList.remove('open');
      navToggle.setAttribute('aria-expanded', 'false');
    });
  });
}

const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.12 });

document.querySelectorAll('.reveal').forEach((el) => observer.observe(el));

const zoomModal = document.getElementById('zoomModal');
const zoomModalImage = document.getElementById('zoomModalImage');
const zoomModalCaption = document.getElementById('zoomModalCaption');
const zoomClose = document.querySelector('.zoom-close');

const getImageCaption = (img) => {
  const imageCard = img.closest('.image-card');
  if (imageCard) {
    const title = imageCard.querySelector('h3')?.textContent?.trim();
    const desc = imageCard.querySelector('p')?.textContent?.trim();
    return [title, desc].filter(Boolean).join(' — ');
  }
  const galleryItem = img.closest('.gallery-item');
  if (galleryItem) {
    return galleryItem.querySelector('span')?.textContent?.trim() || img.alt || 'Imagem ampliada';
  }
  const featureSection = img.closest('.split-section');
  if (featureSection) {
    return 'PDV Legal — Retaguarda';
  }
  const heroCard = img.closest('.hero-image-card');
  if (heroCard) {
    return 'PDV Legal — Tela real do sistema';
  }
  return img.alt || 'Imagem ampliada';
};

const openZoom = (img) => {
  zoomModalImage.src = img.currentSrc || img.src;
  zoomModalImage.alt = img.alt || 'Imagem ampliada';
  zoomModalCaption.textContent = getImageCaption(img);
  zoomModal.classList.add('open');
  zoomModal.setAttribute('aria-hidden', 'false');
  document.body.classList.add('modal-open');
};

const closeZoom = () => {
  zoomModal.classList.remove('open');
  zoomModal.setAttribute('aria-hidden', 'true');
  zoomModalImage.src = '';
  document.body.classList.remove('modal-open');
};

document.querySelectorAll('.hero-image-card img, .feature-image img, .image-card img, .gallery-item img').forEach((img) => {
  img.addEventListener('click', (event) => {
    event.preventDefault();
    event.stopPropagation();
    openZoom(img);
  });
});

document.querySelectorAll('.gallery-item').forEach((item) => {
  item.addEventListener('click', (event) => {
    event.preventDefault();
    const img = item.querySelector('img');
    if (img) openZoom(img);
  });
});

zoomClose?.addEventListener('click', closeZoom);
zoomModal?.addEventListener('click', (event) => {
  if (event.target === zoomModal) closeZoom();
});

document.addEventListener('keydown', (event) => {
  if (event.key === 'Escape' && zoomModal.classList.contains('open')) closeZoom();
});
