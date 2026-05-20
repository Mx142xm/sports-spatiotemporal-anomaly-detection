# Anomaly Detection in Spatiotemporal Sports Data

## Overview

This project investigates anomaly detection in structured spatiotemporal sports data.

The project simulates the movement of a football team as a coordinated multi-agent system and introduces two types of anomalous behaviour: structural disruptions, where several players deviate from the team formation, and positional disruptions, where the team shifts abruptly as a whole.

The goal is to compare standard anomaly detection with a representation-aware approach that incorporates team shape, temporal consistency, and simple rule-based reasoning.

## Research Question

Can anomaly detection be improved by representing team behaviour through structural and temporal features rather than raw player coordinates?

## Data

No external dataset is required. The project uses synthetic football tracking data generated within the notebook.

A team of 10 players is simulated on a two-dimensional football field. At each timestep, each player has x and y coordinates.

## Anomaly Types

The project considers two types of anomalies:

- Structural anomaly: several players move away from the rest of the team, changing the internal formation.
- Positional anomaly: the entire team shifts abruptly while preserving its internal structure.

## Methodology

The project compares three approaches:

1. Baseline Isolation Forest using structural features only.
2. Temporal model adding changes over time and team-center velocity.
3. Hybrid model combining machine learning anomaly scores with rule-based reasoning.

## Features

The feature representation includes:

- Average spread around the team centre
- Average pairwise distance between players
- Convex hull area of the team formation
- Aspect ratio of the team shape
- Changes in structural features over time
- Velocity of the team centre

## Key Findings

- Structural features are informative for detecting formation-level anomalies.
- Adding temporal and positional features improves detection of abrupt collective movement.
- The anomaly-class F1-score improves from approximately 0.70 to 0.73.
- The hybrid model adds interpretability through simple domain-informed rules.
- Structural and positional anomalies require different feature representations.

## Report

The full project report is available here:

[sports_spatiotemporal_anomaly_detection_report.pdf](sports_spatiotemporal_anomaly_detection_report.pdf)

## Repository Structure

```text
sports_spatiotemporal_anomaly_detection.ipynb       Jupyter notebook with the experiment
sports_spatiotemporal_anomaly_detection_report.pdf  Project report
requirements.txt                                    Python dependencies
README.md                                           Project description
