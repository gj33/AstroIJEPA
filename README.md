# 📦 AstroIJEPA

> In this repository we explore the application of the IJEPA model to astronomy data. [Click here](https://github.com/facebookresearch/ijepa) for more details on IJEPA.

---

##  DATA

-  TinyImageNet — we first apply IJEPA to TinyImageNet data as a test.
-  Galaxy Zoo 2 — The [Galaxy Zoo 2 data release](https://arxiv.org/abs/1308.3496) contains images from the Sloan Digital Sky Survey (SDSS). These are external galaxys in the optical regime.
-  MeerKLASS survey — We use [Cata2Data](https://github.com/mb010/Cata2Data) to load cutouts from a pregenerated [PyBdsf Catalogue](https://pybdsf.readthedocs.io/en/latest/) of the large scale contiguous [MeerKLASS survey](https://arxiv.org/abs/1709.06099)

---

## Implementation

We conduct the IJEPA pre-training without labels on each of the three datasets. We edit the IJEPA configurations (learning rate, weight decay, masking parameters etc.) for each dataset. For the MeerKLASS data we make alterations to the IJEPA source code to accommodate data loading from .FITS astronomy file with Cata2Data. We also edit the source code to accommodate single channel inputs rather than the previous three channel inputs. 

Then, we perform fine-tuning with labels and evaluate performance. We also investigate the model latent space. Note that the MeerKLASS survey has no labels so fine-tuning is not possible. The implementation for each dataset is found in the respective folders: 'TinyImageNet', 'GalaxyZoo2' and 'MeerKLASS'.

