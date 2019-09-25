# lifecare
exercice de maison
```
 from django.db import models
from tinymce import HTMLField

# Create your models here.


class clinic(models.Model):
    logo = models.ImageField(blank=True, upload_to='post')
    numero = models.IntegerField()
    adresse = models.EmailField()
    daily = models.CharField(max_length=255)
    localisation = models.CharField(max_length=255)
    email = models.EmailField(max_length=254)
    description = models.CharField(max_length=255)
    lisence = models.CharField(max_length=255)
    actif = models.BooleanField(default=False)
    icon = models.CharField(max_length=250)
    facebook = models.CharField(max_length=50)
    google = models.CharField(max_length=50)
    twitter = models.CharField(max_length=50)
    wifi = models.CharField(max_length=50)
    pinteress = models.CharField(max_length=50)
    youtube = models.CharField(max_length=50)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for clinics."""

        verbose_name = 'clinics'
        verbose_name_plural = 'clinics'

    def __str__(self):
        """Unicode representation of clinics."""
        return self.email



class Bienvenu(models.Model):
    """Model definition for Bienvenu."""

    image = models.ImageField(upload_to='post')
    logo = models.ImageField(upload_to='post')
    text1 = models.CharField(max_length=255)
    text2 = models.CharField(max_length=255)
    text3 = models.CharField(max_length=255)
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Bienvenu."""

        verbose_name = 'Bienvenu'
        verbose_name_plural = 'Bienvenus'

    def __str__(self):
        """Unicode representation of Bienvenu."""
        return self.text1

class Souscription(models.Model):
    """Model definition for Souscription."""

    email = models.EmailField(max_length=254)
    #description = models.CharField(max_length=255)
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Souscription."""

        verbose_name = 'Souscription'
        verbose_name_plural = 'Souscriptions'

    def __str__(self):
        """Unicode representation of Souscription."""
        return self.email


class Message(models.Model):
    """Model definition for Message."""

    nom = models.CharField(max_length=255)
    email = models.EmailField(max_length=254)
    numero = models.IntegerField()
    sujet = models.CharField(max_length=255)
    message = models.CharField(max_length=255)
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Message."""

        verbose_name = 'Message'
        verbose_name_plural = 'Messages'

    def __str__(self):
        """Unicode representation of Message."""
        return self.nom


class Citation(models.Model):
    """Model definition for Citation."""

    titre = models.CharField(max_length=255)
    description = models.CharField(max_length=255)
    image_auteur = models.ImageField(upload_to='post')
    nom = models.CharField(max_length=50)
    job = models.CharField(max_length=50)
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Citation."""

        verbose_name = 'Citation'
        verbose_name_plural = 'Citations'

    def __str__(self):
        """Unicode representation of Citation."""
        return self.titre


class Category_doctor(models.Model):
    """Model definition for Category_doctor."""

    nom = models.CharField(max_length=50)
    description = models.CharField(max_length=50)
    image = models.ImageField(upload_to='post')
    icon = models.CharField(max_length=250)
    

    class Meta:
        """Meta definition for Category_doctor."""

        verbose_name = 'Category_doctor'
        verbose_name_plural = 'Category_doctors'

    def __str__(self):
        """Unicode representation of Category_doctor."""
        return self.nom

# class Reseaux_sociaux(models.Model):
#     """Model definition for Reseaux_sociaux."""

#     doctor_id = models.ForeignKey('Doctor',on_delete=models.CASCADE, related_name='reseaux')
#     clinic = models.ForeignKey('Clinic',on_delete=models.CASCADE, related_name='clinic')
#     liens = models.CharField(max_length=255)
#     image = models.ImageField(upload_to='post')
#     nom = models.CharField(max_length=50)
#     icon = models.CharField(max_length=250)

#     class Meta:
#         """Meta definition for Reseaux_sociaux."""

#         verbose_name = 'Reseaux_sociaux'
#         verbose_name_plural = 'Reseaux_sociauxs'

#     def __str__(self):
#         """Unicode representation of Reseaux_sociaux."""
#         return self.nom



class Doctor(models.Model):
    """Model definition for Doctor."""

    nom = models.CharField(max_length=50)
    image = models.ImageField(upload_to='post')
    job = models.CharField(max_length=50)
    specialite = models.CharField(max_length=50)
    description = models.CharField(max_length=255)
    category_doctor = models.ForeignKey('Category_doctor',on_delete=models.CASCADE, related_name='doctor_category')
    icon = models.CharField(max_length=250)
    facebook = models.CharField(max_length=50)
    github = models.CharField(max_length=50)
    twitter = models.CharField(max_length=50)
    linkedin = models.CharField(max_length=50)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Doctor."""

        verbose_name = 'Doctor'
        verbose_name_plural = 'Doctors'

    def __str__(self):
        """Unicode representation of Doctor."""
        return self.nom

class Rendez_vous(models.Model):
    """Model definition for Rendez_vous."""

    nom = models.CharField(max_length=50)
    email = models.CharField(max_length=255)
    jours = models.CharField(max_length=255)
    heure = models.CharField(max_length=255)
    nom_doctor = models.CharField(max_length=50)
    message = models.CharField(max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)
    icon = models.CharField(max_length=250)

    class Meta:
        """Meta definition for Rendez_vous."""

        verbose_name = 'Rendez_vous'
        verbose_name_plural = 'Rendez_vouss'

    def __str__(self):
        """Unicode representation of Rendez_vous."""
        return self.nom



class Service(models.Model):
    """Model definition for Service."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=255)
    image = models.ImageField(upload_to='post')
    statut = models.BooleanField(default = True)
    icon = models.CharField(max_length=250)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Service."""

        verbose_name = 'Service'
        verbose_name_plural = 'Services'

    def __str__(self):
        """Unicode representation of Service."""
        return self.titre

class Article(models.Model):
    """Model definition for Article."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=255)
    image = models.ImageField(upload_to='post')
    contenu = HTMLField('Content')
    lien = models.CharField(max_length=50)
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Article."""

        verbose_name = 'Article'
        verbose_name_plural = 'Articles'

    def __str__(self):
        """Unicode representation of Article."""
        return self.titre

class Clinic_time(models.Model):
    """Model definition for Clinic_time."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=50)
    logo = models.ImageField(upload_to='post')
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Clinic_time."""

        verbose_name = 'Clinic_time'
        verbose_name_plural = 'Clinic_times'

    def __str__(self):
        """Unicode representation of Clinic_time."""
        return self.titre

class Working_hour(models.Model):
    """Model definition for Working_hour."""

    titre = models.CharField(max_length=50)
    image = models.ImageField(upload_to='post')
    days = models.CharField(max_length=50)
    hours = models.CharField(max_length=50)
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Working_hour."""

        verbose_name = 'Working_hour'
        verbose_name_plural = 'Working_hours'

    def __str__(self):
        """Unicode representation of Working_hour."""
        return self.titre

class Emergence_case(models.Model):
    """Model definition for Emergence_case."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=255)
    image = models.ImageField(upload_to='post')
    icon = models.CharField(max_length=250)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Emergence_case."""

        verbose_name = 'Emergence_case'
        verbose_name_plural = 'Emergence_cases'

    def __str__(self):
        """Unicode representation of Emergence_case."""
        return self.titre

class Hebergement(models.Model):
    """Model definition for Hebergement."""

    titre = models.CharField(max_length=255)
    adresse = models.CharField(max_length=255)
    stockage = models.CharField(max_length=255)
    base_data = models.CharField(max_length=255)
    domaine = models.CharField(max_length=255)
    support = models.CharField(max_length=255)
    image = models.ImageField(upload_to='post')
    prix = models.CharField(max_length=255)
    description = models.CharField(max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)


    class Meta:
        """Meta definition for Hebergement."""

        verbose_name = 'Hebergement'
        verbose_name_plural = 'Hebergements'

    def __str__(self):
        """Unicode representation of Hebergement."""
        return self.titre


class Cart(models.Model):
    """Model definition for Cart."""

    lien = models.CharField(max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Cart."""

        verbose_name = 'Cart'
        verbose_name_plural = 'Carts'

    def __str__(self):
        """Unicode representation of Cart."""
        return self.lien

  
```
