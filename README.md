# lifecare
exercice de maison
```
 from django.db import models

# Create your models here.


class Information(models.Model):
    logo = models.ImageField(blank=True, upload_to='post')
    numero = models.PhoneNumberField()
    adresse = models.EmailField()
    daily = models.CharField(max_length=255)
    localisation = models.CharField(max_length=255)
    email = models.EmailField(max_length=254)
    description = models.CharField(max_length=255)
    lisence = models.CharField(max_length=255)
    pinteress = models.CharField( max_length=255)
    youtube = models.CharField( max_length=255)
    google = models.CharField( max_length=255)
    twitter = models.CharField( max_length=255)
    facebook = models.CharField( max_length=255)
    wifi = models.CharField( max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for informations."""

        verbose_name = 'Informations'
        verbose_name_plural = 'Informations'

    def __str__(self):
        """Unicode representation of Informations."""
        pass



class Bienvenu(models.Model):
    """Model definition for Bienvenu."""

    image = models.ImageField(upload_to='post')
    logo = models.ImageField(upload_to='post')
    text1 = models.CharField( max_length=255)
    text2 = models.CharField( max_length=255)
    text3 = models.CharField( max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Bienvenu."""

        verbose_name = 'Bienvenu'
        verbose_name_plural = 'Bienvenus'

    def __str__(self):
        """Unicode representation of Bienvenu."""
        pass

class Souscription(models.Model):
    """Model definition for Souscription."""

    email = models.EmailField(max_length=254)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Souscription."""

        verbose_name = 'Souscription'
        verbose_name_plural = 'Souscriptions'

    def __str__(self):
        """Unicode representation of Souscription."""
        pass


class Message(models.Model):
    """Model definition for Message."""

    nom = models.CharField(max_length=255)
    email = models.EmailField(max_length=254)
    numero = models.PhoneNumberField()
    sujet = models.CharField(max_length=255)
    message = models.CharField(max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Message."""

        verbose_name = 'Message'
        verbose_name_plural = 'Messages'

    def __str__(self):
        """Unicode representation of Message."""
        pass


class Citation(models.Model):
    """Model definition for Citation."""

    titre = models.CharField(max_length=255)
    description = models.CharField(max_length=255)
    image_auteur = models.ImageField(upload_to='post')
    nom = models.CharField(max_length=50)
    job = models.CharField(max_length=50)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Citation."""

        verbose_name = 'Citation'
        verbose_name_plural = 'Citations'

    def __str__(self):
        """Unicode representation of Citation."""
        pass



class Doctor(models.Model):
    """Model definition for Doctor."""

    nom = models.CharField(max_length=50)
    image = models.ImageField(upload_to='post')
    job = models.CharField(max_length=50)
    specialite = models.CharField(max_length=50)
    description = models.CharField(max_length=255)
    facebook = models.CharField(max_length=255)
    github = models.CharField(max_length=255)
    twitter = models.CharField(max_length=255)
    linkedin = models.CharField(max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Doctor."""

        verbose_name = 'Doctor'
        verbose_name_plural = 'Doctors'

    def __str__(self):
        """Unicode representation of Doctor."""
        pass

class Rendez_vous(models.Model):
    """Model definition for Rendez_vous."""

    nom = models.CharField(max_length=50)
    email = models.CharField(max_length=255)
    jours = models.DateField(auto_now=False, auto_now_add=False)
    heure = models.TimeField(auto_now=False, auto_now_add=False)
    nom_doctor = models.CharField(max_length=50)
    message = models.CharField(max_length=255)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)
    #doctor_id = models.ForeignKey('Doctor', on_delete = models.CASCADE, related_name = 'doctor_rdv',)

    class Meta:
        """Meta definition for Rendez_vous."""

        verbose_name = 'Rendez_vous'
        verbose_name_plural = 'Rendez_vouss'

    def __str__(self):
        """Unicode representation of Rendez_vous."""
        pass



class Service(models.Model):
    """Model definition for Service."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=255)
    image = models.ImageField(upload_to='post')
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Service."""

        verbose_name = 'Service'
        verbose_name_plural = 'Services'

    def __str__(self):
        """Unicode representation of Service."""
        pass

class Article(models.Model):
    """Model definition for Article."""

    titre = models.CharField(max_length=50)
    description = models.CharField( max_length=255)
    image = models.ImageField(upload_to='post')
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Article."""

        verbose_name = 'Article'
        verbose_name_plural = 'Articles'

    def __str__(self):
        """Unicode representation of Article."""
        pass

class Clinic_time(models.Model):
    """Model definition for Clinic_time."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=50)
    logo = models.ImageField(upload_to='post')
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Clinic_time."""

        verbose_name = 'Clinic_time'
        verbose_name_plural = 'Clinic_times'

    def __str__(self):
        """Unicode representation of Clinic_time."""
        pass

class Working_hour(models.Model):
    """Model definition for Working_hour."""

    titre = models.CharField(max_length=50)
    image = models.ImageField(upload_to='post')
    days = models.CharField(max_length=50)
    hours = models.CharField(max_length=50)
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Working_hour."""

        verbose_name = 'Working_hour'
        verbose_name_plural = 'Working_hours'

    def __str__(self):
        """Unicode representation of Working_hour."""
        pass

class Emergence_case(models.Model):
    """Model definition for Emergence_case."""

    titre = models.CharField(max_length=50)
    description = models.CharField(max_length=50)
    image = models.ImageField(upload_to='post')
    statut = models.BooleanField(default = True)
    date_add = models.DateTimeField(auto_now_add= True)
    date_update = models.DateTimeField(auto_now= True)

    class Meta:
        """Meta definition for Emergence_case."""

        verbose_name = 'Emergence_case'
        verbose_name_plural = 'Emergence_cases'

    def __str__(self):
        """Unicode representation of Emergence_case."""
        pass


  
```
